# Remita Inline Sample
> Our Web library lets you easily accept payments inside any web application.

![](payment-image.png)

## Usage

To start using Remita Inline Checkout, refer to the [sample Remita Inline Sample HTML file](remita-inline-sample.html)

Please replace the 'public key' in the script with your assigned API key, which you can obtain by signing up as an integrator on [remita](https://remita.net).

## Development setup

Integrating Remita Inline Checkout is a straightforward process. Include our JavaScript library at the bottom of the checkout form page, like so:
```sh
<form>
    <script src="https://remitademo.net/payment/v1/remita-pay-inline.bundle.js"></script>
    <button type="button" onclick="makePayment()"> Pay </button> 
</form>
<script>
 function makePayment() {
              var form = document.querySelector("#payment-form");
              var paymentEngine = RmPaymentEngine.init({
                  key:'QzAwMDAyNzEyNTl8MTEwNjE4NjF8OWZjOWYwNmMyZDk3MDRhYWM3YThiOThlNTNjZTE3ZjYxOTY5NDdmZWE1YzU3NDc0ZjE2ZDZjNTg1YWYxNWY3NWM4ZjMzNzZhNjNhZWZlOWQwNmJhNTFkMjIxYTRiMjYzZDkzNGQ3NTUxNDIxYWNlOGY4ZWEyODY3ZjlhNGUwYTY=',
                  transactionId: Math.floor(Math.random()*1101233), // Replace with a reference you generated or remove the entire field for us to auto-generate a reference for you. Note that you will be able to check the status of this transaction using this transaction Id
                  customerId: '39832',
                  firstName: 'John',
                  lastName: 'Doe',
                  email: 'john.doe@mailinator.com',
                  amount: 15000,
                  narration: 'Essential Walking Shoes',
                  onSuccess: function (response) {
                      console.log('callback Successful Response', response);
                  },
                  onError: function (response) {
                      console.log('callback Error Response', response);
                  },
                  onClose: function () {
                      console.log("closed");
                  }
              });
               paymentEngine.showPaymentWidget();
          }
</script>

```
## Documentation
For detailed information, refer to [Remita Documentation](https://remita.net/developers/)

## Release History

* 0.1.1
    * CHANGE: Updated documentation
* 0.1.0
    * Initial release
* 0.0.1
    * Work in progress


## Useful links
* Join our Slack Developer/Support channel at [slack](http://bit.ly/RemitaDevSlack)
    
## Support
- For all other support needs, support@remita.net

### Contributing: To contribute to this repository, follow the steps below:

- Fork the repository
- Create a new branch: `git checkout -b feature-name`
- Make changes and commit: `git commit -m "added some new features"`
- Make pushes: `git push origin feature-name`
- Submit a PR (Pull Request)
