# Creating a Workflow for n8n

## Overview

Before we begin, let's look at the workflow overview to understand its structure and appearance.

![overview](../../../assets/workflows/steps/overview.png)

**Note**: If you want to get started quickly, you can reuse [my workflow](../../../exports/N8N%20Auto%20Posting%20Content.json)

- Download the JSON file and import it into n8n
- Update the credentials with your account information (follow the [previous document](../05-workflows/02-create-credentials.md))
- That's it! Your n8n auto-posting content workflow is ready to execute.

## Workflow Steps Overview

| Step | Action                 | Purpose                                      | Platform           |
| ---- | ---------------------- | -------------------------------------------- | ------------------ |
| 1    | Create Workflow        | Initialize new workflow project              | n8n                |
| 2    | Manual Trigger         | Start workflow execution                     | n8n                |
| 3    | Get Google Sheets Data | Retrieve content with 'ready' status         | Google Sheets      |
| 4    | Download Images        | Convert image URLs to binary format          | Google Drive       |
| 5    | Post to LinkedIn       | Share content on LinkedIn                    | LinkedIn           |
| 6    | Post to Facebook       | Share content on Facebook                    | Facebook Graph API |
| 7    | Create WordPress Post  | Upload post without image to WordPress       | WordPress          |
| 8    | Get Images for WP      | Download images for WordPress                | Google Drive       |
| 9    | Upload Media to WP     | Upload images to WordPress                   | WordPress          |
| 10   | Update Media to Post   | Link uploaded media to WordPress post        | WordPress          |
| 11   | Update Sheet Status    | Mark content as posted and increment counter | Google Sheets      |

## Step 1

On the home page, click on 'Create Workflow'.
![step1.1](../../../assets/workflows/steps/step1.1.png)

Next, set the project name to 'N8N Auto Posting Content' and click Save.
![step1.2](../../../assets/workflows/steps/step1.2.png)

Then, click on the 'Add first step...' button.

## Step 2

We will use the Manual trigger node, which means n8n will run the workflow when we click on 'Execute Workflow'.

![step2](../../../assets/workflows/steps/step2.png)

## Step 3

Click on the + button, search for 'Google Sheets', and select it.
![step3.1](../../../assets/workflows/steps/step3.1.png)

We will use the 'Get row(s) in sheet' action to retrieve all content with a status of 'ready'.
![step3.2](../../../assets/workflows/steps/step3.2.png)

Follow the guide below (remember to connect this node with the trigger node from Step 2):

1. Choose your Google Sheets credential connection
2. Select your document (n8n_contents) and sheet index (Sheet1)
3. Add filters to get records with status 'ready':
   - Choose column: status
   - Set value to: 'ready'
4. Click on 'Execute Step'
5. The success or failure result will appear on the right side
   ![step3.3](../../../assets/workflows/steps/step3.3.png)

## Step 4

Click on the + button, search for 'Google Drive', and select it.
![step4.1](../../../assets/workflows/steps/step4.1.png)

We will use the 'Download file' action to convert images from URLs to binary format, as social media platforms only accept images in binary format.
![step4.2](../../../assets/workflows/steps/step4.2.png)

Follow the guide below (remember to connect this node with the Google Sheets node from Step 3):

1. Choose your Google Drive credential connection
2. In the File field, change the dropdown on the left to 'By URL'
3. Drag and drop the 'image' field into the File value field on the right (see image for details)
4. Click on 'Execute Step'
5. The success or failure result will appear on the right side
   ![step4.3](../../../assets/workflows/steps/step4.3.png)

## Step 5

Click on the + button, search for 'LinkedIn', and select it.
![step5.1](../../../assets/workflows/steps/step5.1.png)

Choose the 'Create a post' action.
![step5.2](../../../assets/workflows/steps/step5.2.png)

Follow the guide below (remember to connect this node with the Google Drive node from Step 4):

1. Choose your 'LinkedIn account' credential connection
2. From the top left, change the current tab to 'Schema'
3. Drag and drop the 'content' field into the Text value field in the center (see image for details)
4. In the 'Input Binary Field', enter the value: 'data'
5. Click on 'Execute Step'
6. The success or failure result will appear on the right side
   ![step5.3](../../../assets/workflows/steps/step5.3.png)

## Step 6

Click on the + button, search for 'Facebook Graph API', and select it.
![step6.1](../../../assets/workflows/steps/step6.1.png)

Follow the guide below (remember to connect this node with the Google Drive node from Step 4):

1. Choose your 'Facebook Graph account' credential connection
2. From the top left, change the current tab to 'Schema'
3. Configure the fields:
   - HTTP Request Method: POST (used to create a request for posting new messages to the Facebook API)
   - Graph API Version: Choose the latest version (currently v23.0)
   - Node: me
   - Edge: photos (used for posting new messages with images)
4. Enable 'Send Binary File' and set the Input Binary Field to 'data'
5. In Options, create a new Query Parameter with:
   - Name: message
   - Value: Drag and drop the 'content' field into the Value field (see image for details)
6. Click on 'Execute Step'
7. The success or failure result will appear on the right side
   ![step6.2](../../../assets/workflows/steps/step6.2.png)

# Note: From step 7 ~ 10, please take a note about node name because its will reference on child node fields when reuse later

## Step 7: Upload post without image into wordpress

Find the node **Create a post**, you also can change name of node - just remember name of node
In my case, I will keep this node as name **Create a post**

![step7.1](../../../assets/workflows/steps/step7.1.png)

## Step 8: Create node to get image for wordpress

Repeat [Step 4](#step-4) to create new node download file, but remember in this time we change name of node to **get_images_wp**

![step8.1](../../../assets/workflows/steps/step8.1.png)

## Step 9: Upload image to wordpress

Find and use the node **HTTP Request** then rename it into **Upload media to WP**

![step9.1](../../../assets/workflows/steps/step9.1.png)

Config same as image, just has notice about URL. the syntax of URL will be

```code
${your-url-wordpress} + '/wp-json/wp/v2/media'
```

In my case: `https://litgroup.io/wp-json/wp/v2/media`

![step9.2](../../../assets/workflows/steps/step9.2.png)

- Header parameters:

```code
[
   {
      name: 'content-disposition',
      value: `attachment; filename={{ $binary.data.fileName }}`
   },
   {
      name: 'content-type',
      value: `{{ $binary.data.mimeType }}`
   }
]
```

## Step 10: Update media to Post WP

Find and use the node **HTTP Request** then rename it into **Update media to Post WP**

![step10.1](../../../assets/workflows/steps/step10.1.png)

Config same as image, just has notice about URL. the syntax of URL will be

```code
${your-url-wordpress} + '/wp-json/wp/v2/posts/' + ${posted_id}
```

In my case: `https://litgroup.io/wp-json/wp/v2/posts/{{ $('Create a post').item.json.id }}`

![step10.2](../../../assets/workflows/steps/step10.2.png)

- Header parameters:

```code
[
   {
      name: 'featured_media',
      value: `{{ $('Upload media to WP').item.json.id }}`
   },
]
```

Note: **\$('Create a post')** and **\$('Upload media to WP')** is a name of nodes at [steps 7](#step-7-upload-post-without-image-into-wordpress) and [step 9](#step-9-upload-image-to-wordpress)

## Step 11

Click on the + button, search for 'Google Sheets', and select it.
We will use the 'Update row in sheet' action to update the status to 'posted' and increment the posted_time by 1.
![step12.1](../../../assets/workflows/steps/step12.1.png)

Follow the guide below (remember to connect this node with both the LinkedIn, Facebook and Wordpress nodes from Steps 5, 6 & 10):

1. Choose your 'Google Sheets account' credential connection
2. Configure the fields:
   - Resource: Sheet Within Document
   - Operation: Update Row
   - Document and Sheet: Select your document (n8n_contents) and sheet index (Sheet1)
   - Mapping Column Mode: Map Each Column Manually
   - Column to match on: Select field 'no'
3. In the 'Value to Update' field:
   - Drag and drop the 'no' field into the **no (using to match)** field
     ![step12.2](../../../assets/workflows/steps/step12.2.png)
   - In the status field, set the value to 'posted'
   - In the posted_time field, drag and drop 'posted_time' into the value of posted_time in the center (see image for details), then add `+ 1` before the end of `}}`
     ![step12.3](../../../assets/workflows/steps/step12.3.png)
4. Click on 'Execute Step'
5. The success or failure result will appear on the right side

---

# Reference create N8N connection for Wordpress [here](https://www.youtube.com/watch?v=xioMvEWt-NE)

---

**Previous**: [Create Credentials](./02-create-credentials.md)  
**Next**: [Back to Workflows Overview](./n8n-workflow.md)
