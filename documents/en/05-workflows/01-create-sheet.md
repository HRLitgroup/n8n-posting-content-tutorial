# Creating a Google Sheet to Store Content

## Before You Begin

You can view [my demo sheet](https://docs.google.com/spreadsheets/d/1kZKFQHKA0mLgP5-wGmY56QeT5h9ykyDjNB7hRpOm35U) as a reference.

![Database Structure](../../../assets/workflows/database/gg_sheet_db.png)

## Google Sheet Table Structure

Create a table with the following 6 columns:

| Column          | Description                                                      | Default Value | Notes                                       |
| --------------- | ---------------------------------------------------------------- | ------------- | ------------------------------------------- |
| **no**          | The index number for each content item                           | -             | Unique identifier                           |
| **title**       | The title of the content                                         | -             | Optional - may be used for future features  |
| **content**     | The actual content that will be posted to social media platforms | -             | Main content field                          |
| **image**       | The URL of the image from Google Drive                           | -             | See image documentation below               |
| **status**      | Content status                                                   | `draft`       | Possible values: `draft`, `ready`, `posted` |
| **posted_time** | Number of times content has been posted                          | `0`           | Tracks posting frequency                    |

### Status Values

- `draft`: Content is still in progress
- `ready`: Content is ready to be processed by n8n
- `posted`: Content has been successfully posted to social media

## Google Drive Folder Setup for Images

### Step 1: Create the Folder

In your Google Drive, create a folder named 'N8N Auto Posting Content'

![Google Drive Folder](../../../assets/workflows/database/gg_drive_folder.png)

### Step 2: Grant Permissions

Set the folder permission to 'Anyone with the link' - this allows n8n to download images more easily

![Folder Permissions](../../../assets/workflows/database/gg_drive_folder_permission.png)

---

**Previous**: [Create N8N Workflow](./n8n-workflow.md)  
**Next**: [Create Credentials](./02-create-credentials.md)
