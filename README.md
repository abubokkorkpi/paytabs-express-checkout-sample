Paytabs express checkout sample
========
![Paytabs-express-checkout-v4.0.0](https://img.shields.io/badge/Paytabs%20express%20checkout-v4.0.0-green.svg)

For more information please see [the website][1].


Install
--------

Read the documentation to know how to integrate your application with the library
[documentation v4.0][1]

```html
<script src="https://paytabs.com/express/v4/paytabs-express-checkout.js"
    id="paytabs-express-checkout"
    data-secret-key="merchant_secret_key"
    data-ui-type="iframe"
    data-is-popup="true"
    data-merchant-id="merchant_id"
    data-url-redirect="http://example.com/callback/"
    data-amount="10.0"
    data-currency="SAR"
    data-title="John Doe"
    data-product-names="Iphone"
    data-order-id="25"
    data-customer-first-name="John"
    data-customer-last-name="Deo"
    data-customer-phone-number="5486253"
    data-customer-email-address="john.deo@paytabs.com"
    data-customer-country-code="973"
    data-billing-full-address="Manama, Bahrain"
    data-billing-city="Manama, Bahrain"
    data-billing-state="Manama, Bahrain"
    data-billing-country="BHR"
    data-billing-postal-code="123456"
    />
```
[![Edit static](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/jl87z8jqxv)
## Overview

PayTabs Express Checkout is a solution that provides an efficient checkout process for online
shoppers which keeps them on the merchant’s website while making a payment and even after the
payment is complete.

## Request
> You have to [Login](https://www.paytabs.com/login) to get your `data-secret-key` and `data-merchant-id`

|       Element      |   Description |
| -------------------- | ------------- |
| `data-secret-key` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>     | Merchant Secret Key which is found in <br/> Merchant Dashboard > Navigation Menu > Secret Key    |
| `data-merchant-id` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>    | Merchant ID found at the top-right corner of the Merchant Dashboard. <br/> Example: 10012345   |
| `data-language` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>       | Language `"en"` , `"ar"` <br/> Default `"en"`      |
| `data-url-redirect`<br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>    | Call back URL after payment is successful. <br/>Example: https://www.example.com/payment_result|
| `data-url-cancel`<br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>    | Call back URL after payment is cancelled. <br/> Example: https://www.example.com/payment_cancel </br></br> In case the user closes the popup during the transactions and `data-url-cancel` parameter is not passed in the merchant's Express Checkout button script, a query param <u>is_canceled_pt=1</u> is passed in the return link `data-url-redirect`|
| `data-redirect-on-reject`<br/><label>`Boolean`</label>  | If you wish the cardholder to be redirected to `data-url-redirect` even if the payment is rejected the pass this value as `true`, if you wish the merchant to remain on the same page pass this value as `false`|
| `data-amount` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`Decimal`</label>  | Final amount requested for payment should include the total amount of the products, discount, shipping charges, VAT and any other charges.|
| `data-currency` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>   | Currency of the amount stated. <br> 3 character ISO currency code <br/> Examples:<br/> `USD` for US dollars <br/>`AED` for Emirati Dirham </br>`SAR` for Saudi Riyal|
| `data-title` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>   | Title of the transaction,<br/> Example: Billing for Order 1234, or Bill To Mr. John Doe, etc |
| `data-product-names` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  | For multiple products use comma separated products (i.e: iPhoneX, iPhone, Lightning Dock, iPhone earphones)| 
| `data-order-id` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>   |Order ID generated on merchant's Website. |
| `data-customer-first-name`  <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  |First Name of the Customer |
| `data-customer-last-name` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>   |Last Name of the Customer |
| `data-customer-phone-number`  <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  | Minimum length 6 ,Maximum string length 15 |
| `data-customer-email-address`<br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>   |Email of the customer |
| `data-customer-country-code` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  |International dialing code for Phone Number of the Customer. Please enter country code without ‘0’ or ‘+’ <br/> Example:<br/> UAE country code is `973`<br/>USA country code is `1` | 
| `data-billing-full-address` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  |Full billing Address <br>Multiple address lines will be merged into one single line. </br>maximum string length 60 |
| `data-billing-city` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  |Billing city <br/> maximum string length 50|
| `data-billing-state` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  |Billing state <br/> For USA and Canada please use the correct state and province 2-character codes. <br/>https://www.ups.com/worldshiphelp/WS16/ENU/AppHelp/Codes/State_Province_Codes.htm |
| `data-billing-country` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label>  |Billing country <br/> 3-Character ISO country code. <br/> Examples: <br/>`ARE` for United Arab Emirates<br/>`SAU` for Kingdom of Saudi Arabia<br/>`USA` for United States of America|
| `data-billing-postal-code` <br/> <label style="color:#0075c9">`Required`</label><br/> <label>`String`</label> |Billing postal code <br/> When the billing country is the U.S., the 9-digit postal code must follow this format: `[5 digits][dash][4 digits]`<br/>Example `12345-6789`|

**Shipping address (Optional)**

|       Element      |   Description |
| -------------------- | ------------- |
| `data-shipping-full-address` <br/><label>`String`</label> |Full shipping address.Multiple address lines will be merged into one single line. <br/>maximum string length 60 |
| `data-shipping-city` <br/><label>`String`</label>  |Shipping city <br/> maximum string length 50|
| `data-shipping-state`  <br/><label>`String`</label> |Shipping State <br/>For USA and Canada please use the correct state and province 2-character codes. <br/>https://www.ups.com/worldshiphelp/WS16/ENU/AppHelp/Codes/State_Province_Codes.htm|
| `data-shipping-country` <br/><label>`String`</label>  |Shipping country  <br/> 3-Character ISO country code. <br/> Examples: <br/>`ARE` for United Arab Emirates<br/>`SAU` for Kingdom of Saudi Arabia<br/>`USA` for United States of America |
| `data-shipping-postal-code` <br/><label>`String`</label> |Shipping Postal code <br/> When the billing country is the U.S., the 9-digit postal code must follow this format: `[5 digits][dash][4 digits]`<br/>Example `12345-6789` |

**Customization (Optional parameters)** 

|       Element      |   Description |
| -------------------- | ------------- |
| `data-ui-type` <br/> <label>`String`</label>| User interface implementation, the option allows you to customize express checkout and choose between three different option</br> `Button` Default, Express Checkout Button is displayed and when clicked will load Express Checkout popup <br/>`Iframe` Loads Express Checkout as an embedded iframe <br/>`Click` You can use this with your custom checkout button and use `Paytabs.oPenPaymentPage()` with JS or after ajax requests|
| `data-ui-element-id`<br/> <label>`String`</label>  | Dom element id to show payment page |
| `data-is-popup`<br/> <label>`Boolean`</label>  | Show payment page as popup full screen if you pass as `true` |
| `data-color` <br/> <label>`String`</label> | Payment page theme color <br/> Default color `#0075c9` |
| `data-checkout-button-width` <br/> <label>`String`</label> | Checkout button width |
| `data-checkout-button-height` <br/> <label>`String`</label> | Checkout button height |
| `data-checkout-button-img-url` <br/> <label>`Link`</label> | Checkout button image src |
| `data-ui-show-header` <br/> <label>`Boolean`</label> | To enable or disable the header which includes the logo and close button. <br/> Default value is `true`. |


**Enable transaction features**

|       Element      |   Description |
| -------------------- | ------------- |
| `data-is-preauth` <br/> <label>`Boolean`</label> |Pass `true`, if you wish to authorize the transaction only without capturing it. For more information about using Pre-authorization feature check this link. |
| `data-is-tokenization` <br/> <label>`Boolean`</label> | Pass `true`, if you want to create a new tokenization profile for this transaction. <br/><b>Note:</b> Tokenization feature is only available for some countries. |

Paytabs
--------
[Support][2] | [Terms of Use][3] | [Privacy Policy][4]




 [1]: https://docs.paytabs.com/express-checkout-v4
 [2]: https://www.paytabs.com/en/support/
 [3]: https://www.paytabs.com/en/terms-of-use/
 [4]: https://www.paytabs.com/en/privacy-policy/