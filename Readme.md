node-postageapp
=====

PostageApp Node.js Module for easier way to send email from web apps

Usage
------------

Request

	var p = require('postageapp');
	
	p.recipients = '[{"joesmith@gmail.com","michaelrogers@gmail.com","filipodivincy@crazy.com"}]';
	p.subject = "Hello Guys, You have Won $20000000! towards your college certificate";
	p.from = "paul@nigeria.com";
	p.type = "html";
	p.attachments = "/tmp/scam-application.doc";
	p.template = fs.readFileSync("/tmp/scam-application.tpl","utf8");
	p.variables = '{"header": "Congratulation!", "footer_note": "For PHDs click on link below"}
	var r = p.send();
	

Successful Reponse

	{ "response" : {
	    "uid" : "27cf6ede7501a32d54d22abe17e3c154d2cae7f3",
	    "status" : "ok"
	  },
	  "data" : {
	    "message" : {
	      "id" : "1234567890"
	    }
	  }
	}

Bad Response

	{ "response" : {
	    "uid" : "27cf6ede7501a32d54d22abe17e3c154d2cae7f3",
	    "status" : "bad_request",
	    "message" : "Some error message. Like: you forgot the recipients!"
	  }
	}