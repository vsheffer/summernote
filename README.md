# My notes on building using docker...

** NOTE: ** I am not at all a JS/Node/Yarn developer so I just learn
enough to hack the code for my purposes, so this section is for people
like me who want to get directly to how you can build a production 
distribution that you can use in your applications.

You build the distribution of Summernote using **yarn**.  I do not like
installing a bunch of node/js/blah blah related tools into my host so I
always build using Docker.  When I was searching for an image the first 
couple of highest search results did not work.  The following command
will get you into a shell terminal that will allow you to build all of the 
supported distributions:

```
docker run \
  -it \
  --rm \
  -v $(pwd):/host \
  jitesoft/node-yarn /bin/sh
```

Once in the shell you can do the following:
```
cd /host
yarn upgrade
yarn build
```

# Summernote

Super simple WYSIWYG Editor.

[![Build Status](https://travis-ci.org/summernote/summernote.svg?branch=develop)](http://travis-ci.org/summernote/summernote)
[![npm version](https://badge.fury.io/js/summernote.svg)](http://badge.fury.io/js/summernote)
[![Coverage Status](https://coveralls.io/repos/summernote/summernote/badge.svg?branch=develop&service=github)](https://coveralls.io/github/summernote/summernote?branch=develop)

### Summernote
Summernote is a JavaScript library that helps you create WYSIWYG editors online.

Home page: <https://summernote.org>

### Why Summernote?

Summernote has a few special features:

* Paste images from clipboard
* Saves images directly in the content of the field using base64 encoding, so you don't need to implement image handling at all
* Simple UI
* Interactive WYSIWYG editing
* Handy integration with server
* Supports Bootstrap 3, 4 and 5 integrations
* Lots of [plugins and connectors](https://github.com/summernote/awesome-summernote) provided together

### Installation and dependencies

Summernote is built on [jQuery](http://jquery.com/).

#### 1. Include JS/CSS

Include the following code in the `<head>` tag of your HTML:

```html
<!-- include libraries(jQuery, bootstrap) -->
<script type="text/javascript" src="//code.jquery.com/jquery-3.6.0.min.js"></script>
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" />
<script type="text/javascript" src="cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"></script>

<!-- include summernote css/js-->
<link href="summernote-bs5.css" rel="stylesheet">
<script src="summernote-bs5.js"></script>
```

#### 2. Target a element

Then place a `div` tag somewhere in the `body` tag. This element will be replaced with the summernote editor.

```html
<div id="summernote">Hello Summernote</div>
```

#### 3. Summernote it!

Finally, run this script after the DOM is ready:

```javascript
$(document).ready(function() {
  $('#summernote').summernote();
});
```

For more examples, please visit to [homepage](http://summernote.org/examples).

### API

`code` - get the HTML source code underlying the text in the editor:

```javascript
var html = $('#summernote').summernote('code');
```

For more detail about API, please refer to [document](http://summernote.org/getting-started/#basic-api).

#### Warning - code injection

The code view allows the user to enter script contents. Make sure to filter/[sanitize the HTML on the server](https://github.com/search?l=JavaScript&q=sanitize+html). Otherwise, an attacker can inject arbitrary JavaScript code into clients.

### For contributing
https://github.com/summernote/summernote/blob/develop/.github/CONTRIBUTING.md

### Contacts
* Facebook user group: https://www.facebook.com/groups/summernote
* Summernote Slack: [Join the Summernote Slack community](https://communityinviter.com/apps/summernote/summernote)

## Testing powered by
<a target="_blank" href="https://www.browserstack.com/"><img width="200" src="https://www.browserstack.com/images/layout/browserstack-logo-600x315.png"></a><br>
[BrowserStack Open-Source Program](https://www.browserstack.com/open-source)


### License
Summernote may be freely distributed under the MIT license.
