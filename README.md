# Cally for Pebble Config

Cally for Pebble is a Pebble smartwatch app that allows you to quickly add items to a Google calendar using speech.

This repository contains a node.js app, used by the Cally for Pebble app to authenticate with Google using OAuth.

See [******TODO*****](https://github.com/alirawashdeh/wundervoice) on github for the source code of the Pebble application itself.

## Configuration

Sign up for API keys at [Google Developer](https://console.developers.google.com).

Modify the following part of the app.js file to include your client ID and client secret:

```
var client_id = process.env.client_id || '03ffe0cac0a0401aa6673c3cf6d02ced';// Your client id
var client_secret = process.env.client_secret || 'a57c43efb9644574a96d6623fb8bfbc2'; // Your client secret
```

Alternatively, if you're deploying to heroku, you can set the relevant environment variables instead:

```sh
$ heroku config:set client_id=03ffe0cac0a0401aa6673c3cf6d02ced
$ heroku config:set client_secret=a57c43efb9644574a96d6623fb8bfbc2
```

Once you have deployed your application, take a note of the URL and update the following part of the app.js file:

```
var redirect_uri = process.env.redirect_uri || 'http://localhost:8888/callback'; // Your redirect uri
```

Remember, OAuth requires that callback URLs are hosted using SSL, so ensure that you specify an "HTTPS" URL.

Make sure you then configure the same callback URL against your application at [Wunderlist Developer](https://developer.wunderlist.com).

# Credits

Thanks to heroku/node-js-getting-started and spotify/web-api-auth-examples for the vast majority of this code.
