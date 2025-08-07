# Connect LinkedIn to N8N

## 🎯 What Are We Setting Up?

**LinkedIn** is the world's largest professional networking platform. By connecting it to N8N, you can automate posting professional content, sharing articles, and managing your professional presence automatically.

### ✅ What You'll Get

- Automatically post professional content to LinkedIn
- Share articles and updates automatically
- Manage your professional profile
- Track engagement and analytics
- Build your professional network efficiently

## 🛠️ What You Need Before Starting

Make sure you have:

- ✅ A LinkedIn account (personal or business)
- ✅ A LinkedIn company page (optional but recommended)
- ✅ About 10-15 minutes to complete the setup
- ✅ Your LinkedIn password ready

## 📋 Step-by-Step Setup

### Step 1: Create Your LinkedIn App

Think of this as creating a "bridge" between LinkedIn and N8N:

1. **Open your web browser**
2. **Go to LinkedIn Developers**: [Click here to visit](https://www.linkedin.com/developers/apps)
3. **Sign in with your LinkedIn account** if prompted
4. **Click "Create App"** (usually a blue button)

### Step 2: Fill in Your App Details

1. **App name**: "My N8N LinkedIn Automation"
2. **LinkedIn Page**:
   - If you have a company page, select it
   - If not, you can create one or use your personal profile
3. **App logo**: Upload any image (this is just for identification)
4. **App description**: "Automation tool for LinkedIn posting"
5. **Check the box**: "I have read and agree to these terms"
6. **Click "Create App"**

### Step 3: Set Up Security (OAuth Settings)

This tells LinkedIn that your automation is safe to use:

1. **In your app dashboard**, look for the "Auth" tab
2. **Click on "Auth"**
3. **Find "OAuth 2.0 settings"**
4. **Add this redirect URL**: `http://localhost:5678/rest/oauth2-credential/callback`
5. **Click "Save"**

### Step 4: Request Permissions

This step asks LinkedIn for permission to post on your behalf:

1. **Go to the "Products" tab**
2. **Look for these products** and request access to each:

   - **Sign In with LinkedIn using OpenID Connect**
   - **Share on LinkedIn**
   - **LinkedIn Ad Library** (optional)

3. **For each product**:
   - Click on it
   - Click "Request Access"
   - Fill in any required information
   - Submit the request

### Step 5: Get Your Access Keys

These are the "keys" that N8N will use to access LinkedIn:

1. **Go back to the "Auth" tab**
2. **Look for "Client Credentials"**
3. **Note down these important numbers**:
   - **Client ID**: A long string of letters and numbers
   - **Primary Client Secret**: Another long string (keep this secret!)

## ✅ How to Check if Setup Worked

1. **You should have your Client ID and Client Secret** written down
2. **Your app should show as "Active"** in the dashboard
3. **The redirect URL should be saved** in OAuth settings
4. **You should have requested access** to the products you need

## 🚨 Troubleshooting

### Can't Find the Create App Button?

- **Make sure you're signed in** to the right LinkedIn account
- **Try refreshing the page**
- **Check that you're on the developers page**: linkedin.com/developers/apps

### App Creation Failed?

- **Try a different app name** (maybe it's already taken)
- **Make sure you filled in all required fields**
- **Check that you agreed to the terms**

### OAuth Settings Not Saving?

- **Make sure the redirect URL is exactly**: `http://localhost:5678/rest/oauth2-credential/callback`
- **Try copying and pasting** the URL instead of typing it
- **Check that you clicked "Save"**

### Can't Request Product Access?

- **Some products might take time** to be approved
- **Try requesting them one by one**
- **Make sure you filled in all required information**

### Still Having Problems?

- **Try creating a new app** with a different name
- **Check that you're using the right LinkedIn account**
- **Make sure you have admin access** to your LinkedIn account

## 🎉 You're Ready for the Next Step!

Once you have your LinkedIn credentials set up, you can:

1. **Connect Facebook**: [Set up Facebook automation](./03-get-access-token-for-facebook.md)
2. **Connect Google**: [Set up Google automation](./01-get-access-token-for-google.md)
3. **Start creating workflows**: Use LinkedIn in your N8N automations

## 📚 Additional Resources

- **Need help?** Check [LinkedIn API documentation](https://developer.linkedin.com/docs)
- **Want to learn more?** Try [LinkedIn OAuth guide](https://developer.linkedin.com/docs/oauth2)
- **N8N specific help**: [N8N LinkedIn integrations](https://docs.n8n.io/integrations/nodes/n8n-nodes-base.linkedin/)

---

_💡 **Tip**: Keep your Client ID and Client Secret safe. You'll need them when connecting to N8N later._
