s2ap-quickstart-java
==============================

This sample demonstrates integration of the basic components of the Save to Android Pay API.  Review the [quickstart guide](https://developers.google.com/commerce/wallet/objects/quickstart-java) to run the sample.

This sample showcases several aspects of the API
* Creation of Classes and Objects
* Save to Android Pay insertion of classes and objects
* The Web Service API

##Creation of Classes and Objects
The code for creation of classes and objects can be found under the src/com/google/wallet/objects/verticals directory.  Each Object type, such as loyalty, is broken out into its own file.  Classes are inserted using the WobInsertServlet.

## Save to Android Pay insertion of classes and objects
Save to Android Pay is handled on both the client and server.  The index.html file is the landing page for the application and includes app.js.  The app.js file makes a request to the WobGenerateJwtServlet to generate Object type-specific JWTs. You must update the origins list in WobGenerateJwtServlet to run this on a domain other than localhost. The app.js file inserts the appropriate g:savetoandroidpay tags and the Save to Android Pay JavaScript after all of the JWTs are generated.  The JavaScript must be appended after the g:savetoandroidpay tags because it parses the page to render Save to Android Pay buttons when it's completed loading.

## Webservice API
The Webservice API handler is WobWebserviceHandlerServlet.  This servlet handles Webservice requests, generates Loyalty Objects, converts Loyalty Objects to JWTs, and responds with the JWT.  The URL to this handler is defined within the war/web.xml file.  You can configure your discoverable to point to the URL handled by WobWebserviceHandlerServlet.

[![Analytics](https://ga-beacon.appspot.com/UA-46956809-1/walletobjects-quickstart-java/README.md)](https://github.com/igrigorik/ga-beacon)
