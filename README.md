nor-pgrunner
============

Utility which can be used to start PostgreSQL server instances temporarely. Good for testing.

### TODO

We use [Trello board](//trello.com/b/aq9cAAiG/nor-pgrunner) to organize development and keep track on things to do.

### Installation

Install from NPM: `npm install -g pgrunner`

### Usage over CLI

Use with CLI:

```
pgrunner create
pgrunner destroy
```

### Usage over Node.js

Use with Node.js:

```
var pgrunner = require('nor-pgrunner');
```

Example usage:

```
pgrunner({
	'host': '127.0.0.1',  // Defaults to '127.0.0.1'
	'port': 55432,        // Defaults to '55432'
	'user': 'foo',        // Defaults to USER from ENV
	'database': 'dbname'  // Defaults to same value as the user option
}).then(function(server) {
	
	// server.pgconfig is a string like 'pg://jhh@127.0.0.1:55432/jhh'
	// server.settings has the same options as properties: host, port, user, database
	// server.env has the environment variables the server is using
	
	// Stop the instance
	return server.stop().then(function() {
		console.log('Stopped successfully');
	});

}).fail(function(err) {
	console.log('Error: ' + err);
}).done();
```

Commercial Support
------------------

You can buy commercial support from [Sendanor](http://sendanor.com/software).
