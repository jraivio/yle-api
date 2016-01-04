# yle-api [![Build Status](https://travis-ci.org/jsalonen/yle-api.svg?branch=master&cachebust=1)](https://travis-ci.org/jsalonen/yle-api) [![Coverage Status](https://coveralls.io/repos/jsalonen/yle-api/badge.svg?branch=master&service=github&cachebust=1)](https://coveralls.io/github/jsalonen/yle-api?branch=master)

Unofficial Node.js SDK for Yle API

**Work in progress. All contributions (pull requests, issues, comments) welcome!**

## Requirements

Requires node.js v4.0.0 or later.

You must provide the SDK with your developer API keys. The keys can be ordered from the official developer site at: http://developer.yle.fi/.

Note that terms of service apply to any usage of the API, including this SDK.

## Using Command-line Tools

For command-line use, you may prefer installing globally with:

        npm install -g yle-api

Authorize the command-line tools with your API keys as follows:

- Copy `.yleapi-EXAMPLE` into your home folder and rename it to `.yleapi`
- Edit the file to add your own API keys

Now try out the command-line tool:

	yle-api search uutiset

If everything went well, a list of results should be returned.

### Program search

Refine the search with optional parameters:

	yle-api search uutiset --availability=ondemand --order=publication.starttime:desc

For documentation, check help:

	yle-api search --help

## Using as a Node.js/JavaScript Library

Install and add as a dependency:

	npm install --save yle-api

Simple usage example:

```js
var yleapi = require('yle-api');
var client = new yleapi.Client({
  appId: '[YOUR_APP_ID]',
  appKey: '[YOUR_APP_KEY]',
  decryptKey: '[YOUR_DECRYPT_KEY]'
});

client.getPrograms({q: 'Uutiset'}, function(err, programs) {
  console.log(programs);
});
```

Check out the source code for more methods.
