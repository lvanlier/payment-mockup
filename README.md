# payment-mockup

This is an extract from a ’larger mockup’ (sfdx project) with only the relevant extracts :
Classes
Lwc

And kind of an extract from the node.js stuff :
Node code (extract)
Pages (see view -> .handlebars)
 
This is readable but not runnable !
 
In this the sequence is :
 
(1) The SF/LWC : paymentPage.js triggers the process

(2) This goes to the node.js app.get('/paymentGW/makepayment', (re, res) => … which uses the sdk and then return the viewPaymentPage.handlebars

(3) The users complete the payment on Worldline

(4) Worldline calls back what has been configured as manual and auto return urls

(5) The ‘manual’  goes to the node.je app.post('/paymentGW/paymentreturnforsf', (re, res) => {…  which sends back to SF the viewPaymentStatusPage.handlebars

(6) The ‘auto’ goes to app.post('/paymentGW/paymentreturnurlauto', (re, res) => { that just logs the status on the console of the node server
 
I use ngrok to allow the connection between SF and localhost
