# Connect Facebook to N8N

## 🎯 What Are We Setting Up?

**Facebook** is the world's largest social media platform. By connecting it to N8N, you can automate posting to Facebook pages, sharing content, and managing your social media presence automatically.

### ✅ What You'll Get

- Automatically post content to Facebook pages
- Share content across multiple pages
- Manage business page content
- Track social media performance
- Save time on social media management

## 🛠️ What You Need Before Starting

Make sure you have:

- ✅ A Facebook account
- ✅ A Facebook Business Page (recommended for business use)
- ✅ About 10-15 minutes to complete the setup
- ✅ Your Facebook password ready

## 📋 Step-by-Step Setup

### Step 1: Create Your Facebook App

Think of this as creating a "bridge" between Facebook and N8N:

1. **Open your web browser**
2. **Go to Facebook Developers**: [Click here to visit](https://developers.facebook.com/apps/)
3. **Sign in with your Facebook account** if prompted
4. **Click "Create App"** (usually a blue button)

### Step 2: Choose Your App Type

1. **In the "Add use cases" section**, you'll see different options
2. **Choose "Other"** → **"Business"**
3. **Click "Create App"**
4. **After creating the app**, look for the product called `Facebook Login for Business`
5. **Click "Set up"** next to it

### Step 3: Configure Your App Settings

This step sets up the basic information for your app:

1. **In your app dashboard**, go to "App Settings" → "Basic"
2. **Note down these important numbers**:

   - **App ID**: A long string of numbers
   - **App Secret**: Another long string (keep this secret!)

3. **Find "Privacy Policy URL"** and enter:

   - You can use this URL: `https://www.notion.so/Privacy-Policy-23bcdfbb0c61807fadd7f76ba4ef59fe`
   - Or create your own using [Notion](https://www.notion.so)

4. **Click "Save Changes"**

### Step 4: Make Your App Live

This step allows your app to work properly:

1. **Look for a toggle button** that says "Live" or "Development"
2. **Click the toggle** to switch it to "Live" mode

![Set Live](../../../assets/facebook/fb-live.png)

### Step 5: Generate Your Access Token

This creates the "key" that N8N will use to access Facebook:

1. **From the menu bar**, click "Tools" → "Graph API Explorer"

![Graph API Explorer](../../../assets/facebook/facebook-graph-api.png)

2. **In "Meta App"**, select your app from the dropdown
3. **In "User or Page"**, select "Get Page Access Token"
4. **You'll need to log in** with your Facebook account
5. **Choose the page** you want to access

![Grant Access](../../../assets/facebook/fb-grant-access.png)

6. **Click "Save"**

### Step 6: Add Permissions

This tells Facebook what your automation can do:

1. **Look for "Permissions"** section
2. **Add these permissions** one by one:

   - `pages_show_list`
   - `business_management`
   - `attribution_read`
   - `page_events`
   - `pages_read_engagement`
   - `pages_manage_posts`

3. **Click "Generate Access Token"**
4. **Click "Copy"** to copy your access token

![Copy Access Token](../../../assets/facebook/facebook-copy-access-token.png)

### Step 7: Extend Your Token (Make It Last Longer)

Facebook tokens expire quickly, so we need to extend them:

1. **From "Tools"**, select "Access Token Debugger"

![Token debug](../../../assets/facebook/facebook-token-debug.png)

2. **Paste your token** that you copied earlier
3. **Click "Debug"**
4. **Scroll to the bottom** and you'll see "Extend Access Token"
5. **Click "Extend Access Token"**
6. **Copy the new token** (it will be green) - this one lasts longer

## ✅ How to Check if Setup Worked

1. **You should have your App ID and App Secret** written down
2. **Your app should be in "Live" mode**
3. **You should have generated an access token**
4. **You should have extended the token** (the green one)

## 🚨 Troubleshooting

### Can't Find the Create App Button?

- **Make sure you're signed in** to the right Facebook account
- **Try refreshing the page**
- **Check that you're on the developers page**: developers.facebook.com/apps

### App Creation Failed?

- **Try a different app name** (maybe it's already taken)
- **Make sure you chose "Other" → "Business"**
- **Check that you're using the right Facebook account**

### Can't Generate Access Token?

- **Make sure you're logged in** to Facebook
- **Check that you selected the right page**
- **Try refreshing the Graph API Explorer**

### Token Not Working?

- **Make sure you extended the token** (the green one)
- **Check that you copied the entire token**
- **Try generating a new token** if the old one expired

### Still Having Problems?

- **Try creating a new app** with a different name
- **Check that you're using the right Facebook account**
- **Make sure you have admin access** to your Facebook page

## 🎉 You're Ready for the Next Step!

Once you have your Facebook credentials set up, you can:

1. **Connect Google**: [Set up Google automation](./01-get-access-token-for-google.md)
2. **Connect LinkedIn**: [Set up LinkedIn automation](./02-get-access-token-for-linkedin.md)
3. **Start creating workflows**: Use Facebook in your N8N automations

## 📚 Additional Resources

- **Need help?** Check [Facebook Graph API documentation](https://developers.facebook.com/docs/graph-api)
- **Want to learn more?** Try [Facebook OAuth guide](https://developers.facebook.com/docs/facebook-login/security)
- **N8N specific help**: [N8N Facebook integrations](https://docs.n8n.io/integrations/nodes/n8n-nodes-base.facebook/)
- **Test your setup**: [Graph API Explorer](https://developers.facebook.com/tools/explorer/)

---

_💡 **Tip**: Keep your App ID, App Secret, and extended access token safe. You'll need them when connecting to N8N later._
