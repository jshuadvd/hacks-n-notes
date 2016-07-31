# Sending email

- **SMTP** (Simple Mail Transfer Protocol) allows to send emails
- **MSA** (Mail Submission Agent) delivers emails through trusted channels. Handles temporary outages & bounced emails (eg. SendGrid, Gmail)
- nodemailer is an npm package to send emails by Andris Reinman

## HTML Email

- [ ] [About writting HTML Email](http://kb.mailchimp.com/campaigns/ways-to-build/about-html-email)
- [ ] [HTML email boiler plate](https://github.com/seanpowell/Email-Boilerplate)
- [ ] [Lithmus for testing](http://litmus.com/email-testing)


```js
app.post('/cart/checkout', (req, res) => {
  var cart = req.session.cart;
  if(!cart) next(new Error('Cart does not exist'));
  var name = req.body.name || '', email = req.body.email || '';
    // input validation
    if (!email.match(VALID_EMAIL_REGEX))
      return res.next(new Error('Invalid email address.'));

    // assign a random cart ID; normally we would use a database ID here
    cart.number = Math.random().toString().replace(/^0\.0*/, '');
  cart.billing = {
    name,
    email
  };
  res. render('email/cart-thank-you', { layout: null, cart: cart },
    (err, html) => {
      if(err) console.log('error in email template');
      mailTransport.sendMail({
        from: '"Meadowlark Travel": info@meadowlarktravel.com',
        to: cart.billing.email,
        subject: 'Thank You for Book your Trip with Meadolark',
        html,
        generateTextFromHtml: true
      }, (err) => {
        if (err) console.error('Unable to send confirmation: ' + err.stackk);
      })
    }
  )
  res.render('cart-thank-you', {cart})
});
```
