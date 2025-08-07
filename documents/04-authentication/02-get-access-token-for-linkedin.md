# Get LinkedIn API Access Token for N8N

## Overview

This guide provides step-by-step instructions for obtaining LinkedIn API access tokens that can be used in N8N workflows for LinkedIn marketing, networking automation, and social media management.

## Prerequisites

Before starting, ensure you have:

- A LinkedIn account
- A LinkedIn company page
- Basic understanding of API authentication concepts

## Step 1: Create a LinkedIn App

1. Go to [LinkedIn Developers Apps](https://www.linkedin.com/developers/apps)
2. Click "Create App"
3. Fill in the app details:
   - **App name**: "n8n-posting-content"
   - **LinkedIn Page**: Select your company page (or create one)
   - **App logo**: Upload a logo for your app
   - **App description**: Brief description of your app's purpose
   - Check the checkbox `I have read and agree to these terms`
4. Click "Create App"

## Step 2: Configure OAuth 2.0 Settings

1. In your app dashboard, go to the "Auth" tab
2. Under "OAuth 2.0 settings", add redirect URLs: `http://localhost:5678/rest/oauth2-credential/callback`
3. Click "Save"

### Configure App Permissions

1. Go to the "Products" tab
2. Request access to the products you need:
   - **Sign In with LinkedIn using OpenID Connect**
   - **Share on LinkedIn**
   - **LinkedIn Ad Library**

## Step 3: Get Client Credentials

1. In your app dashboard, go to the "Auth" tab
2. Note down your credentials:
   - **Client ID**: Your app's unique identifier
   - **Primary Client Secret**: Your app's secret key (keep this secure)

## Next Steps

Once you have successfully configured LinkedIn API access:

**Proceed to Next Platform**: Continue with [Facebook API Setup](./03-get-access-token-for-facebook.md)

## Additional Resources

- [LinkedIn API Documentation](https://developer.linkedin.com/docs)
- [LinkedIn OAuth 2.0 Guide](https://developer.linkedin.com/docs/oauth2)
- [N8N LinkedIn Integrations](https://docs.n8n.io/integrations/nodes/n8n-nodes-base.linkedin/)
- [LinkedIn Developers Portal](https://www.linkedin.com/developers/)
