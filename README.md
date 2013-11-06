wallet-objects-quickstart-java
==============================

This sample demonstrates integration of the basic components of the Wallet Objects API.  Review the [quickstart guide](https://developers.google.com/commerce/wallet/objects/quickstart-java) to run the sample.

This sample showcases several aspects of the API
* Creation of Wallet Classes and Wallet Objects
* Save to Wallet insertion of classes and objects
* The Web Service API

##Creation of Wallet Classes and Wallet Objects
The code for creation of classes and objects can be found under the src/com/google/wallet/objects/verticals directory.  Each Wallet Object type, such as loyalty, is broken out into its own file.  Classes are inserted using the WobInsertServlet.

## Save to Wallet insertion of classes and objects
Save to Wallet is handled on both the client and server.  The index.html file is the landing page for the application and includes app.js.  The app.js file makes a request to the WobGenerateJwtServlet to generate Wallet Object type-specific JWTs. You must update the origins list in WobGenerateJwtServlet to run this on a domain other than localhost. The app.js file inserts the appropriate g:wallet tags and the Save to Wallet JavaScript after all of the JWTs are generated.  The JavaScript must be appended after the g:wallet tags because it parses the page to render Save to Wallet buttons when it's completed loading.

## Webservice API
The Webservice API handler is WobWebserviceHandlerServlet.  This servlet handles Webservice requests, generates Loyalty Objects, converts Loyalty Objects to JWTs, and responds with the JWT.  The URL to this handler is defined within the war/web.xml file.  You can configure your discoverable to point to the URL handled by WobWebserviceHandlerServlet.
