# IRIS Pay OpenCart 4 Extension

This extension integrates IRIS Pay into your OpenCart 4 store.

## Installation Steps for Production

### 1. Uploading Files
You have two options to install the extension:

#### Option A: Manual Upload (Recommended for quick testing)
1. Copy the contents of the `extension/irispay` folder directly into your server's `extension/irispay` directory.
   - Files structure on server should be:
     - `extension/irispay/admin/...`
     - `extension/irispay/catalog/...`
     - `extension/irispay/install.json`

#### Option B: OpenCart Installer (Standard way)
1. Prepare the ZIP file:
   - **Automated**: If you have a bash terminal (Git Bash, Linux, macOS), run `./build.sh` from the root of the repository. This will generate `irispay.ocmod.zip`.
   - **Manual**: Create a ZIP file containing the contents of the `upload` folder (`admin`, `catalog`, and `install.json`). Name it `irispay.ocmod.zip`.
2. Go to **Admin -> Extensions -> Installer**.
3. Click **Upload** and select your ZIP file.


### 2. Enable the Extension
1. Go to **Admin -> Extensions -> Extensions**.
2. Select **Payments** from the dropdown menu.
3. Find **IRIS Pay** and click the green **Install** (+) button.
4. Click the **Edit** (pencil) button to configure the module.

### 3. Configuration
Fill in the following details provided by IRIS Pay:
*   **API Key**: The API Key provided by IRIS Pay.
*   **Environment**: Select "Sandbox" for testing or "Live" for real payments.
*   **SDK Version**: Select the SDK version to load ("Production" or "Developer").
*   **Status**: Set to **Enabled**.

### 4. Webhook Setup
1. Copy the **Webhook URL** displayed at the bottom of the IRIS Pay configuration page in OpenCart.
2. Log in to your **IRIS Pay Portal**.
3. Go to Webhook settings and paste the URL.
4. Ensure the webhook status is **Active**.

## Features
- Seamless integration with OpenCart 4 checkout.
- Automatic order status updates via webhooks.
- Support for multiple terminal failure statuses (Cancelled, Expired, Rejected).
- Real-time payment status polling.

## Support
For technical support or issues, please contact the IRIS Pay development team.
