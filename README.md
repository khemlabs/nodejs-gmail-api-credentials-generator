## Gmail API credentials

This nodejs app helps you to generate valid gmail api credentials

[Official documentation and original code](https://developers.google.com/gmail/api/quickstart/nodejs)

### Run APP

```bash
node index.js
```

* __You need to download the credential JSON file from Google.__
* __The app will create a file with the tokens at ~/.credentials/gmail-nodejs-quickstart.json__

### Environment variables

* SCOPE: comma separated values
* CLIENT_SECRET_PATH: path to the credentials file __[defaulf: ./client_secret.json]__

### Download file with *client_id* and *client_secret*

1. __Step one:__ Create or select a proyect in [HERE](https://console.developers.google.com/start/api?id=gmail)
```
You should see a select input, where you can select previous projects or create a new one
```
2. __Step two:__ Click in __go to credentials__ button
```
You should be in https://console.developers.google.com/apis/credentials/wizard?api=gmail.googleapis.com&project=[project_name]
```
3. __Step three:__ Click in __cancel__
```
You should be in https://console.developers.google.com/apis/credentials?showWizardSurvey=true&project=[project_name]
```
4. __Step four:__ Click in __create credentials__
4. __Step five:__ Click in __oauth credentials__
5. __Step five:__ Click in __other__
6. __Step five:__ Download file selecting it from credentials table

### Use credentials with nodemailer

```nodejs
var nodemailer = require("nodemailer");

var transporter = nodemailer.createTransport({
    service: "gmail",
    auth: {
        type: "OAuth2",
        user: 'email_that_created_the_app@gmail.com,
        clientId: "clientId",
        clientSecret: "clientSecret",
        refreshToken: "refreshToken"
    }
});
```
