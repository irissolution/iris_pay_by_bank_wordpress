# IRIS Pay for WooCommerce

This plugin integrates the **IRIS Pay WebSDK** payment gateway into WooCommerce, allowing your customers to pay directly and securely via their bank accounts.

## Features
- Deep integration with the IRIS Pay v8/v9 API architecture.
- Frontend rendering using the native `<irispay-component>` WebSDK.
- Fully automated order status synchronization (Pending -> Processing / Failed).
- Built-in status polling and direct sever-to-server webhook confirmation.
- Selectable Endpoints (Sandbox / Production) and UI SDK Versions (Dev / Prod).

---

## 📥 Installation

1. Download the `irispay-woocommerce.zip` archive.
2. Log in to your WordPress Admin Dashboard.
3. Navigate to **Plugins -> Add New**.
4. Click the **Upload Plugin** button at the top of the page.
5. Choose the `irispay-woocommerce.zip` file and click **Install Now**.
6. Once installed, click **Activate Plugin**.

*(ℹ️ Native WooCommerce MUST be installed and activated prior to enabling this gateway).*

---

## ⚙️ Configuration

1. In your WordPress Admin, go to **WooCommerce -> Settings**.
2. Click on the **Payments** tab.
3. Find **IRIS Pay** in the list of payment methods and click **Manage** (or toggle the 'Enable' switch).
4. Configure the following fields:
    - **Enable/Disable:** Check to enable the gateway on checkout.
    - **API Key:** Enter your official IRIS Pay API Key (Sandbox or Live).
    - **Environment:** Choose **Sandbox** for testing, or **Production (Live)** for real transactions.
    - **SDK Version:** Select between the Production SDK or Development SDK.
    
    *(ℹ️ The plugin dynamically fetches the Public Hash, Destination IBAN, and Merchant Name from the IRIS Pay server using your API Key. Setup is now simpler than ever!)*
5. Click **Save changes**.

---

## 🪵 Diagnostics & Troubleshooting

To troubleshoot webhook delivery or status updates, the plugin writes detailed real-time logs to:
`wp-content/irispay.log`

Ensure that the web server has write permissions to the `wp-content` directory.

---

## 🚀 Usage Notes

### Block Checkout vs. Classic Checkout
As of WooCommerce 8.3+, the default checkout page uses the new "Checkout Block" which hides classic payment gateways. 
To ensure IRIS Pay displays correctly:
1. Go to **Pages -> All Pages** and Edit your **Checkout** page.
2. Remove the "Checkout Block".
3. Add a standard "Shortcode" block and paste: `[woocommerce_checkout]`
4. **Update** the page. IRIS Pay will immediately become visible to your customers.
