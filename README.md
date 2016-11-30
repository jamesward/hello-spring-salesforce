Hello Spring Salesforce
=======================

This is a simple Spring Boot application that connects to Salesforce via the REST APIs.


Run on Heroku:

1. Deploy this app on Heroku: [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)
1. [Create a new Connected App on Salesforce](https://login.salesforce.com/app/mgmt/forceconnectedapps/forceAppEdit.apexp)
1. Fill in the `Connected App Name`, `API Name`, and `Contact Email` fields
1. Select `Enable OAuth Settings` and enter the following `Callback URLs`:

        https://YOUR_HEROKU_APP_NAME.herokuapp.com/login
        http://localhost:8080/login

1. Select `Full access (full)` from the list of OAuth Scopes and click `Add`
1. Click `Save` and them `Continue` to complete the creation of the new Connected App
1. Manage the settings for your Heroku app (via the [Heroku Dashboard](https://dashboard.heroku.com)) and add `SECURITY_OAUTH2_CLIENT_CLIENT_ID` and `SECURITY_OAUTH2_CLIENT_CLIENT_SECRET`config vars using the values from the newly created Connected App
1. Wait about 10 minutes until the OAuth app creation is completed
1. Check out your your new app


Run Locally:

1. If you haven't already done so, create a Salesforce Connected App following the instructions above
1. Create a file in the root project directory named `application.properties` that contains:

        security.oauth2.client.client-id = YOUR_CONNECTED_APP_CLIENT_ID
        security.oauth2.client.client-secret = YOUR_CONNECTED_APP_CLIENT_SECRET

    Note: Make sure you do not put this file in SCM!

1. Start the local server via Gradle:

    Mac & Linux:

        ./gradlew dev

    Windows:

        gradlew dev

1. Check out the app: [http://localhost:8080](http://localhost:8080)
