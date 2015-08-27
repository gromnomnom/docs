# Docs

## Integrating the GROM Widget

This tutorial helps you integrate the GROM Widget into your site.

### Here's an overview of what you'll accomplish in this tutorial:

1. Embed the GROM Widget to your site and link it up with GROM via your GROM API Key, which we will generate for you prior to your integration
2. Test the GROM Widget by customizing a mobile phone case
3. Obtain a unique token for the customized mobile phone case
   Note: We will keep a reference to the customized case via this token
4. Send us a list of all your successfully processed orders, with the token of each customized case so we may identify it in our system for fulfillment
   Note: Make sure to include shipping address and any customer info we may need to fulfill the order from our end

#### Step 1: Embed the GROM Widget

To get started, add the following HTML, to where you want to add the GROM Widget to appear:

```
<div id="grom-widget"></div>
<script src="https://w.grom.io/bundle.js"></script>
<script>
  window.addEventListener("message", receiveMessage, false);

  function receiveMessage(event) {
    if (event.origin !== "https://w.grom.io")
      return;

    // ... write your integration code
    // event.data.gromOrderToken shall contain the unique token you'll
    // need to communicate with us about the purchase of the case
    // that had been customized
  }
</script>
```

#### Step 2: Customize a mobile phone case

Go ahead, try it out: customize a phone case in the page where you had dropped in the above code. Click `Add to Cart`. This is what your customer would do when interacting with the Widget.

When you clicked `Add to Cart`, a unique token was generated on our end to identify the customized case. After you had clicked `Add to Cart`, via the browser's native Window.postMessage() API. See the code block above to know how to extract the token. 

#### Step 3: Obtain a unique token for the customized mobile phone case

The token identifies both the digital representation of the customized case, as well as the physical 3d printed case, if the buyer completes the purchase on your end. Effectively, the token represents and allows you to track a lifecycle that a case takes from the moment it is customized by your customer, to the moment your buyer receives it in the mail.

#### Step 4: Use the token to communicate with GROM

The token allows us and you to track the customized phone case that your customer will have customized. For example: this token will allow you to determine the status of whether the phone case had been 3d printed. It will also allow you to tell us the address where to ship the case, after your customer will have paid for the case and completed the order. Please make sure to send us a list of all the tokens, for those transactions in your system, which had completed successfully. In this list you should include the unique token you received, the shipping address of your customer, and any other information you'd like to us to have about the order, that you believe will be important for us to reconcile your order with our system, and vice versa.  
