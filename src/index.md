title: Web Payments - London JS, Sep 2017
description: Web Payments - Introducing new browser APIs for easier online purchases
output: public/index.html
theme: peter-theme
themecolour: 111111
url: https://poshaughnessy.github.io/web-payments-londonjs-2017/
image: https://poshaughnessy.github.io/web-payments-londonjs-2017/images/preview.jpg
controls: false
--

![Web](images/game-art/web-goldcoins.svg)
![Payments](images/game-art/payments-goldcoins.svg)
### Introducing new browser APIs for easier online purchases

<div class="contact">
  <p class="social">[@poshaughnessy](https://twitter.com/poshaughnessy), [@samsunginternet](https://twitter.com/samsunginternet)</p>
  <p class="social">Feat. [@zfdesign](https://twitter.com/zfdesign), [@justeat_tech](https://twitter.com/justeat_tech)</p>
</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-caption five-images

![Very long form 1](images/very-long-checkout-form-1.png) ![Very long form 2](images/very-long-checkout-form-2.png) ![Very long form 3](images/very-long-checkout-form-3.png) ![Very long form 4](images/very-long-checkout-form-4.png) ![Very long form 5](images/very-long-checkout-form-5.png)

###😱

-- bg-goomba

## 69% of shopping carts are abandoned

<div class="caption">Source: [Baymard Institute](https://baymard.com/lists/cart-abandonment-rate)</div>

<div class="credit">[Flavio Ensiki](https://www.flickr.com/photos/flavouz/5086859227)</div>

-- bg-booghost

## 84% abandonment rate on mobile

<div class="caption">Source: [Cloud.IQ via econsultancy.com](https://econsultancy.com/blog/64343-checkout-abandonment-mobile-ux-examples-to-help-boost-conversions/)</div>

<div class="credit">[Fujoshi Bijou](https://www.flickr.com/photos/fujoshi/4277809127)</div>

-- img-with-caption

![Cart abandoment reasons](images/cart-abandonment-reasons-trans.png)

<div class="caption">[baymard.com/lists/cart-abandonment-rate](https://baymard.com/lists/cart-abandonment-rate)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- bg-marioblock bg-fade what-if

### What if...

![Saved details](images/payment-request-remembered-details.png)

<div class="caption">Your browser could securely remember your payment & shipping details?</div>

<div class="credit">[Leandro Amato](https://www.flickr.com/photos/grunge/2829427342)</div>

-- bg-marioblock bg-fade what-if four-images pay-logos

### What if...

![Samsung Pay](images/samsung-pay-logo-white.png)
![Android Pay](images/android-pay-logo-white.png)
![Apple Pay](images/apple-pay-logo-white.png)
![PayPal](images/paypal-logo-white.svg)

<div class="caption">You could use your favourite payment app, in an open standard way?</div>

<div class="credit">[Leandro Amato](https://www.flickr.com/photos/grunge/2829427342)</div>

-- bg-marioblock bg-fade what-if

### What if...

![Fingerprint scan](images/fingerprint-s8.png)

<div class="caption">You could simply confirm payment with your fingerprint or iris scan?</div>

<div class="credit">[Leandro Amato](https://www.flickr.com/photos/grunge/2829427342)</div>

-- img-with-caption bg-insertcoin bg-fade

# Web Payments

<div class="caption">[www.w3.org/Payments/WG/](https://www.w3.org/Payments/WG/)</div>

<div class="credit">[Jan W](https://www.flickr.com/photos/63883151@N07/8486121888)</div>

--

## &ldquo;A revolution in payments on the Web&rdquo;

<div class="caption">Adrian Hope-Bailie</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

[![Payment Request API spec](images/payment-request-api-spec.png)](https://www.w3.org/TR/payment-request/)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- gold-coins bg-mariocoin1 bg-fade

## Let's sell some socks

![Socks](images/socks-emoji-purple.png) ![Gold coins](images/game-art/goldcoin2/coins-less.svg)

<div class="credit">[Aviery Edison](https://www.flickr.com/photos/kylemhayes/3746664569)</div>

<!-- -- -->
<!-- ![Sock sale](images/payment-request-socks-simple.png) -->
<!-- <div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div> -->

--

<video controls>
  <source src="videos/socks-megastore-simple.mp4"/>
  <source src="videos/socks-megastore-simple.webm"/>
</video>

<div class="caption">[samsunginter.net/examples/socks-megastore/after-simple/](http://samsunginter.net/examples/socks-megastore/after-simple/)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
if (window.PaymentRequest) {
  // We're good to go...
} else {
  // Alas! Use your traditional checkout form...
}
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
var methodData = [{
  supportedMethods: ['basic-card']
}];
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
var details = {
  total: {
    label: 'Lovely socks', 
    amount: {currency: 'GBP', value: '12.00'}
  }
};
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
// Show payment UI and handle result

new PaymentRequest(methodData, details)
  .show()
  .then(function(paymentResponse) {
    // Process via gateway/processor, then...
    paymentResponse.complete('success');
  })
  .catch(function(error) {
    // Unable to complete, e.g. user cancelled
  });
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- gold-coins bg-mariocoin2 bg-fade

## Let's add some options

![Socks](images/socks-emoji-purple.png) ![More gold coins](images/game-art/goldcoin2/coins-more.svg)

<div class="credit">[Kent Brewster](https://www.flickr.com/photos/kentbrew/2550957151)</div>

--

```javascript
var details = {
  displayItems: [
    ...
    {
      label: "Loyalty discount",
      amount: { currency: "GBP", value : "-1.00" },
    }
  ],
  total: {
    label: 'Total', 
    amount: {currency: 'GBP', value: '11.00'}
  },
  ...
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>
  
--

```javascript
  ...
  shippingOptions: [
    {
      id: 'standard',
      label: 'Standard shipping',
      amount: {currency: 'GBP', value: '1.50'},
      selected: true
    }
  ]
};
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
var options = {
  requestPayerName: true,
  requestPayerEmail: true,
  requestPayerPhone: true,
  requestShipping: true
};

new PaymentRequest(methodData, details, options)
  ...
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

<video controls>
  <source src="videos/socks-megastore-options.mp4"/>
  <source src="videos/socks-megastore-options.webm">  
</video>

<div class="caption">[samsunginter.net/examples/socks-megastore/after-options/](http://samsunginter.net/examples/socks-megastore/after-options/)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>
  
--

### Better than autofill

* More accurate
* Form pre-built for you!
* Built-in validation
* Optimised for mobile
* 3rd party apps

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

## UX

<button id="express-checkout">Express Checkout</button>

<div class="caption">Could be a good way to integrate it, but up to you, test it out!</div>

-- gold-coins bg-mariowall bg-fade-less

## Let's see where we can use it

<div class="credit">[Phil Romans](https://www.flickr.com/photos/mdu2boy/512643409)</div>

-- browser-support four-images

## Browser support

<div class="container">
  <div>
    ![Chrome for Android](images/chrome-android.png)
    <p>Chrome for Android v53+</p>
  </div>
  <div>
    ![Samsung Internet](images/sbrowser5.4.png)
    <p>Samsung Internet v5.0+</p>
  </div>
  <div>
    ![Chrome](images/chrome.png)
    <p>Chrome desktop v61+</p>
  </div>
  <div>
    ![Edge Preview](images/edge.png)
    <p>Edge v15+</p>
  </div>
</div>

<div class="caption">[caniuse.com/#feat=payment-request](http://caniuse.com/#feat=payment-request)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- browser-support three-images

#### Also in the Working Group...

<div class="container">
  <div>
    ![Firefox](images/firefox.png)
    <p>Mozilla</p>
  </div>
  <div>
    ![Safari](images/safari.png)
    <p>Apple</p>
  </div>
  <div>
    ![Facebook](images/facebook.png)
    <p>Facebook</p>
  </div>
</div>

<div class="caption">[And many more](https://www.w3.org/2004/01/pp-impl/83744/status)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

![Chrome desktop UI](images/chrome-desktop-socks.png)

<div class="caption">Desktop Chrome</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

![DeX UI](images/dex-desktop-socks.png)

<div class="caption">Samsung DeX</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

![Safari Tech Preview](images/safari-tech-preview.jpg)

<div class="caption">[Not working yet](https://twitter.com/marcosc/status/906170462069071874) in Safari Tech Preview but officially [in development](https://webkit.org/status/#feature-payment-request)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>


-- gold-coins bg-mariopipes bg-fade-less

## Let's dive deeper...

<div class="credit">[Neil Girling](https://www.flickr.com/photos/carnivillain/5810033092)</div>

-- more-code

```javascript
  paymentRequest.addEventListener('shippingaddresschange', function(event) {    
    // Say we check the address and we can offer these options:    
    event.updateWith({  
        shippingOptions: [  
          {  
            id: 'standard',  
            label: 'Standard Shipping (5-7 Days)',  
            amount: {value: '0', currency: 'GBP'}  
          }, {  
            id: 'express',  
            label: 'Express Shipping (2-3 Days)',  
            amount: {value: '3.50', currency: 'GBP'}  
          }  
        ],  
      ...
  
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>
  
--

```javascript    
  const paymentDetails = {    
    // Or if we can't offer any shipping to this address
    shippingOptions: [],  
    ...
  };  
  event.updateWith(paymentDetails);  
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>
  
--

```javascript
if (paymentRequest.canMakePayment) {
  paymentRequest.canMakePayment().then(result => {
    if (result) {
      // User has an active payment method
    } else {
      // No active payment method yet, but user can add
    }
  }).catch(function(error) {
    // Unable to determine
  });
}
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

### Payment Response

![Payment response data format](images/payment-response.png)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header payment-gateways

![Payment parties](images/web-payments-parties.png)

<div class="caption">Payment Gateways / Payment Processors / Payment Service Providers (PSPs)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

<!-- img-with-header -->
<!-- ![Polykart](images/polykart.png) -->
<!-- <div class="caption">[polykart-credential-payment.appspot.com](https://polykart-credential-payment.appspot.com/)</div> -->
<!-- <div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div> -->

--

### Example PSP: WePay

![WePay docs screenshot](images/wepay-screenshot.png)

```javascript
WePay.wallet.beginTokenization(...);
```

<div class="caption">[developer.wepay.com/docs/mobile/payment-request-api](https://developer.wepay.com/docs/mobile/payment-request-api)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

![Android Pay](images/android-pay-logo-white.png)

<div class="caption">[bit.ly/payment-request-android-pay](http://bit.ly/payment-request-android-pay)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

<!-- -- -->
<!-- ![Native app integration](images/app-types.png) -->
<!-- <div class="caption">From [w3.org/TR/payment-handler/](www.w3.org/TR/payment-handler/)</div> -->
<!-- <div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div> -->

--

![Android Pay flow](images/android-pay-flow.png)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

![Android Pay tokens explanation](images/android-pay-tokens-explanation.png) 

<div class="caption">[developer.vantiv.com/docs/DOC-1689](https://developer.vantiv.com/docs/DOC-1689)</div>

<div class="caption">("PAN" = Primary Account N​umber, the number embossed on your card)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

<!-- -- img-with-header -->
<!-- #### Gateway Token -->
<!-- ![Gateway token](images/android-pay-gateway-token.png) -->
<!-- <div class="caption">[developers.google.com/android-pay/mobile-web/tutorial](https://developers.google.com/android-pay/mobile-web/tutorial)</div> -->
<!-- <div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div> -->
<!-- -- img-with-header -->
<!-- #### Network Token -->
<!-- ![Network token](images/android-pay-network-token.png) -->
<!-- <div class="caption">[developers.google.com/android-pay/mobile-web/tutorial](https://developers.google.com/android-pay/mobile-web/tutorial)</div> -->
<!-- <div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div> -->

-- more-code

```javascript 
supportedMethods: ['https://android.com/pay'],
data: {  
  merchantName: 'Android Pay Demo',
  // merchant ID obtained from Google that maps to your origin
  merchantId: '01234567890123456789',  
  environment: 'TEST',  
  allowedCardNetworks: ['AMEX', 'DISCOVER', 'MASTERCARD', 'VISA'],  
  paymentMethodTokenizationParameters: {  
    tokenizationType: 'GATEWAY_TOKEN',  
    parameters: {  
      'gateway': 'stripe',  
      'stripe:publishableKey': 'xx_demo_xxxxxxxxxxxxxxxxxxxxxxxx',  
      'stripe:version': '2016-07-06',  
    }  
  }  
}
```

<div class="caption">Android Pay calls your processor and returns a token</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
request.show().then(function(result) {
    // POST the result to server
    return fetch('/pay', {
      method: 'POST',
      body: JSON.stringify(result.toJSON()),
      ...
    })
    // Then check response status & JSON &
    // call result.complete() with 'success' / 'fail'
```

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

#### Apple Pay Wrapper

![Apple Pay wrapper demo](images/apple-pay-wrapper.png)

<div class="caption">[github.com/GoogleChrome/appr-wrapper](https://github.com/GoogleChrome/appr-wrapper)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

```javascript
let method = [{
  supportedMethods: ['https://apple.com/apple-pay'],
  data: {
    supportedNetworks: [
      'amex', 'discover', 'masterCard', 'visa'
    ],
    countryCode: 'US',
    validationEndpoint: '/applepay/validate/',
    merchantIdentifier: 'merchant.com.agektmr.payment'
  }
}];
```

<div class="caption">[github.com/GoogleChrome/appr-wrapper](https://github.com/GoogleChrome/appr-wrapper)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- gold-coins bg-mariocartridges bg-fade

## Let's see some real examples

<div class="credit">[Humberto Rodriguez](https://www.flickr.com/photos/rapapu/4862441304)</div>

-- img-with-header just-eat

![Just Eat](images/just-eat.svg)

<img src="images/game-art/goldcoin/coin-spin.gif" style="width: 2em" alt="Spinning coin"/>

<div class="caption">Demo from [Zlatin Ivanov](https://twitter.com/zfdesign)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

<video controls>
  <source src="videos/just-eat-demo.mp4"/>
  <source src="videos/just-eat-demo.webm"/>
</video>

<div class="caption">Just Eat's prototype Payment Request integration demo'd by [Zlatin Ivanov](https://twitter.com/zfdesign)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>


-- img-with-header

### Monzo 

![Monzo Payment Request](images/monzo3.jpg)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

--

[![Monzo tweet](images/monzo-tweet.png)](https://twitter.com/_dancannon/status/884840037120192512)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header

### Get Your Guide

![Get Your Guide Payment Request](images/get-your-guide.png)

-- quote

#### &ldquo;Our only challenge was adjusting our back-end... we managed to add the API within 20 minutes and adjust the flow within another 2 hours&rdquo; 

<div class="caption">[Get Your Guide](http://inside.getyourguide.com/blog/2016/10/31/payment-request-api/)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- logos

### Also using Payment Request

![Washington Post](images/washingtonpost-white.png) ![Groupon](images/groupon-white.png) ![WWF](images/wwf-white-outline.png) ![JD Sports](images/jdsports.png) ![Nivea](images/nivea-white.png)

-- bg-marioblock bg-fade what-if

## What's next?

<div class="credit">[Leandro Amato](https://www.flickr.com/photos/grunge/2829427342)</div>

-- img-with-header mobile-app-integrations

### More payment apps

![Samsung Pay](images/samsung-pay.png)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- img-with-header payment-handler-api

### Payment Handler API

![Payment Handler API](images/payment-handler-api.png)

<div class="caption">[bit.ly/payment-handler-api](http://bit.ly/payment-handler-api)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

<!-- -- -->
<!-- ### Lots More... -->
<!-- * Payment Method Manifest -->
<!-- * Basic Credit Transfer Payment -->
<!-- * Tokenised Card Payment -->
<!-- * Web Payments HTTP API 1.0 -->
<!-- <div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div> -->

-- more-code

```javascript
// With your service worker registration
return Promise.all([
  registration.paymentManager.instruments.set(
    "dc2de27a-ca5e-4fbd-883e-b6ded6c69d4f",
    {
      name: "Visa ending ****4756",
      enabledMethods: ["basic-card"]
    }),

  registration.paymentManager.instruments.set(
    "c8126178-3bba-4d09-8f00-0771bcfd3b11",
    {
      name: "My Bob Pay Account: john@example.com",
      enabledMethods: ["https://bobpay.com/"]
    })
]);
```

<div class="caption">[w3c.github.io/payment-handler/#register-example](https://w3c.github.io/payment-handler/#register-example)</div>

-- img-with-header

![Payment Handler flag in Chrome](images/payment-handler-chrome.jpg)

<div class="caption">[Currently behind flags in Chrome for Android](https://lists.w3.org/Archives/Public/public-payments-wg/2017Jun/0006.html)</div>

-- img-with-header

### Cryptocurrencies?

![Bitcoin funds for Brave](images/bitcoin-brave.png)

<div class="credit">[brave.com](https://www.brave.com/)</div>

-- img-with-header

[![Brendan Eich tweet](images/brendan-eich-tweet.png)](https://twitter.com/BrendanEich/status/907625611652325376)

<div class="caption">BAT = Basic Attention Token - [basicattentiontoken.org](https://basicattentiontoken.org/)</div>

-- img-with-header medium-clap

#### Beyond the ad-driven Web

![Medium clap](images/mediumclap60fps.gif)

<div class="caption">[Medium's new clap feature. Imagine something similar for throwing a few pennies!](https://twitter.com/poshaughnessy/status/898061485645103105)</div> 

<div class="credit">[Liam Murphy](https://dribbble.com/lemurf)</div>

-- bg-mariotoys and-more

### Gift cards / coupons?

### Tokenisation standardisation?

## And more!

<div class="caption">[www.w3.org/Payments/WG/](https://www.w3.org/Payments/WG/)</div>

<div class="credit">[Hawken King](https://www.flickr.com/photos/hawken/332539130)</div>

-- img-with-header-and-caption

### Web Auth

![Web Auth spec](images/web-auth.png)

<div class="caption">[w3c.github.io/webauthn/](https://w3c.github.io/webauthn/)</div>

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- further-resources

These slides are at

### [bit.ly/webpayments-londonjs-17](https://bit.ly/webpayments-londonjs-17)

Further resources

* [github.com/w3c/webpayments/wiki](https://github.com/w3c/webpayments/wiki)
* [github.com/w3c/payment-request-info](https://github.com/w3c/payment-request-info)
* [github.com/w3c/payment-request-info/wiki/FAQ](https://github.com/w3c/payment-request-info/wiki/FAQ)
* [medium.com/samsung-internet-dev/how-to-take-payments-on-the-web-with-the-payment-request-api-a523f6fc7c1f](https://medium.com/samsung-internet-dev/how-to-take-payments-on-the-web-with-the-payment-request-api-a523f6fc7c1f)
* [github.com/SamsungInternet/examples/tree/master/socks-megastore](https://github.com/SamsungInternet/examples/tree/master/socks-megastore)
* [developers.google.com/web/fundamentals/discovery-and-monetization/payment-request/](https://developers.google.com/web/fundamentals/discovery-and-monetization/payment-request/)

<div class="credit">[Ray Che](https://www.flickr.com/photos/rayche1989/5203972988)</div>

-- thanks bg-mariohooray

### Thanks! Questions? Comments?

![Spinning coin](images/game-art/goldcoin/coin-spin.gif)

<div class="contact">
  <p class="social">[@poshaughnessy](https://twitter.com/poshaughnessy), [@samsunginternet](https://twitter.com/samsunginternet)</p>
  <p class="social">Feat. [@zfdesign](https://twitter.com/zfdesign), [@justeat_tech](https://twitter.com/justeat_tech)</p>
</div>

<p style="font-size: 0.9em;">Please leave us feedback on Meetup</p>

<div class="credit">[Laurence Vagner](https://www.flickr.com/photos/redisdead/2165783016)</div>
