trello-api-form
===============

An HTML form front end that feeds into Trello.com's API and generates automatic e-mail notifications via PHP.

##Introduction
Trello.com is a free Web-based project management tool that organizes data via "cards" inside "lists", similar to a wall of virtual sticky notes. This project:

- Presents an HTML form front end that receives information from the user
- Validates that information via Parsley
- Submits that information to Trello.com via their API, generating a card in a list
- E-mails the requestor a confirmation e-mail via PHP with the request information and the ID of the request number
- Redirects the user to a request received page

##Dependencies
- jQuery: http://jquery.com/
- bootstrap: http://getbootstrap.com/
- bootstrap-datetimepicker: http://eonasdan.github.io/bootstrap-datetimepicker/
- ParsleyJS: http://parsleyjs.org/
- RequireJS: http://requirejs.org/

##Compatibility
- HTML5shiv: https://code.google.com/p/html5shiv/
- RespondJS: https://github.com/scottjehl/Respond

##Configuration

There are 3 separate files you need to edit for this to work:
1. /js/main.js
2. /js/trello-form.js
3. /php/trello-confirmation.php

In main.js:
`"trello": "https://api.trello.com/1/client.js?key=aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",`
should be replaced with your 32-bit application key, which you can generate at https://trello.com/1/appKey/generate.

In trello-form.js:
````
var settings = {
	token: "yourCodeGoesHere-aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
	idList: "yourIdListGoesHere-aaaaa",
	confUrl: "./php/trello-confirmation.php",	
	received: "received.html"
};
````
**token** must be replaced with your application token, which you can generate at https://trello.com/1/authorize?key=substitutewithyourapplicationkey&scope=read%2Cwrite&name=My+Application&expiration=never&response_type=token.

**idList** must be replaced with the id number of the list you want these cards to be generated under. To get this, Add a card>Open card>Share and More>Export to JSON> Look for idList.

##Questions

Any questions, concerns or problems please feel free to reach out to me.
