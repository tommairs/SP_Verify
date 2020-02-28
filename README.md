# SP_Verify
A quick email based user identity verification tool

Sometimes what you need is the verification of user identity (Challenge/Response) like with a Captcha, or SMS confirmation.  

This little tool provides an email based user verification tool using SparkPost.

This involves:
1) Configure Inbound Relay_Webhooks in SparkPost to collect messages. https://developers.sparkpost.com/api/relay-webhooks/
2) Pipe the data from the Relay_Webhook to a process that verifies the secret code you will eventually send a user.
3) Write a relatively basic script to generate a random code to send for verification and store it temporarily for verification.


The process
1) A user signs up for the service, and your internal script generates a random code for them and stores it temporarily
2) Send the user an email with the generated secret code with a link that allows them to One-Click verify.
3) that one-click verify sends the code back to parkPost right to your relay_webhook where we pass it to your application4) Your application verifies that the email address matches the secret code and you let them use the system.

So... it is not prebuilt and turn-key, but it is super easy to implement.  
