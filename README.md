# api documentation for  [prerender-node (v2.7.0)](https://github.com/prerender/prerender-node#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-prerender-node.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-prerender-node) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-prerender-node.svg)](https://travis-ci.org/npmdoc/node-npmdoc-prerender-node)
#### express middleware for serving prerendered javascript-rendered pages for SEO

[![NPM](https://nodei.co/npm/prerender-node.png?downloads=true)](https://www.npmjs.com/package/prerender-node)

[![apidoc](https://npmdoc.github.io/node-npmdoc-prerender-node/build/screenCapture.buildNpmdoc.browser.%252Fhome%252Ftravis%252Fbuild%252Fnpmdoc%252Fnode-npmdoc-prerender-node%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-prerender-node/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-prerender-node/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-prerender-node/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Todd Hooper"
    },
    "bugs": {
        "url": "https://github.com/prerender/prerender-node/issues"
    },
    "dependencies": {
        "request": "^2.40.0"
    },
    "description": "express middleware for serving prerendered javascript-rendered pages for SEO",
    "devDependencies": {
        "mocha": "~1.13.0",
        "nock": "^2.7.0",
        "sinon": "~1.7.3",
        "supertest": "^1.0.1"
    },
    "directories": {},
    "dist": {
        "shasum": "719ad91ae34f773fdc731516849a01849433e7d4",
        "tarball": "https://registry.npmjs.org/prerender-node/-/prerender-node-2.7.0.tgz"
    },
    "gitHead": "6791a9ac90ee1661ef941dbba37c1d00acc7aa37",
    "homepage": "https://github.com/prerender/prerender-node#readme",
    "keywords": [
        "angular",
        "backbone",
        "emberjs",
        "seo"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "thoop",
            "email": "todd@prerender.io"
        },
        {
            "name": "homeyer",
            "email": "homeyer@gmail.com"
        }
    ],
    "name": "prerender-node",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/prerender/prerender-node.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "2.7.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module prerender-node](#apidoc.module.prerender-node)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>afterRenderFn (err, req, prerender_res)](#apidoc.element.prerender-node.afterRenderFn)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>beforeRenderFn (req, done)](#apidoc.element.prerender-node.beforeRenderFn)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>blacklisted (blacklist)](#apidoc.element.prerender-node.blacklisted)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>buildApiUrl (req)](#apidoc.element.prerender-node.buildApiUrl)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>getPrerenderServiceUrl ()](#apidoc.element.prerender-node.getPrerenderServiceUrl)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>getPrerenderedPageResponse (req, callback)](#apidoc.element.prerender-node.getPrerenderedPageResponse)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>gunzipResponse (response, callback)](#apidoc.element.prerender-node.gunzipResponse)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>plainResponse (response, callback)](#apidoc.element.prerender-node.plainResponse)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>set (name, value)](#apidoc.element.prerender-node.set)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>shouldShowPrerenderedPage (req)](#apidoc.element.prerender-node.shouldShowPrerenderedPage)
1.  [function <span class="apidocSignatureSpan">prerender-node.</span>whitelisted (whitelist)](#apidoc.element.prerender-node.whitelisted)
1.  object <span class="apidocSignatureSpan">prerender-node.</span>crawlerUserAgents
1.  object <span class="apidocSignatureSpan">prerender-node.</span>extensionsToIgnore
1.  object <span class="apidocSignatureSpan">prerender-node.</span>prerenderServerRequestOptions



# <a name="apidoc.module.prerender-node"></a>[module prerender-node](#apidoc.module.prerender-node)

#### <a name="apidoc.element.prerender-node.afterRenderFn"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>afterRenderFn (err, req, prerender_res)](#apidoc.element.prerender-node.afterRenderFn)
- description and source-code
```javascript
afterRenderFn = function (err, req, prerender_res) {
  if (!this.afterRender) return;

  this.afterRender(err, req, prerender_res);
}
```
- example usage
```shell
...
    "Content-Type": "text/html"
  });
  return res.end(cachedRender.body || '');
}
    }

    prerender.getPrerenderedPageResponse(req, function(err, prerenderedResponse){
prerender.afterRenderFn(err, req, prerenderedResponse);

if(prerenderedResponse){
  res.writeHead(prerenderedResponse.statusCode, prerenderedResponse.headers);
  return res.end(prerenderedResponse.body);
} else {
  next(err);
}
...
```

#### <a name="apidoc.element.prerender-node.beforeRenderFn"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>beforeRenderFn (req, done)](#apidoc.element.prerender-node.beforeRenderFn)
- description and source-code
```javascript
beforeRenderFn = function (req, done) {
  if (!this.beforeRender) return done();

  return this.beforeRender(req, done);
}
```
- example usage
```shell
...
var request = require('request')
  , url = require('url')
  , zlib = require('zlib');

var prerender = module.exports = function(req, res, next) {
  if(!prerender.shouldShowPrerenderedPage(req)) return next();

  prerender.beforeRenderFn(req, function(err, cachedRender) {

if (!err && cachedRender) {
  if (typeof cachedRender == 'string') {
    res.writeHead(200, {
      "Content-Type": "text/html"
    });
    return res.end(cachedRender);
...
```

#### <a name="apidoc.element.prerender-node.blacklisted"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>blacklisted (blacklist)](#apidoc.element.prerender-node.blacklisted)
- description and source-code
```javascript
blacklisted = function (blacklist) {
  prerender.blacklist = typeof blacklist === 'string' ? [blacklist] : blacklist;
  return this;
}
```
- example usage
```shell
...
app.use(require('prerender-node').whitelisted(['/search', '/users/.*/profile']));
'''

### Blacklist

Blacklist a single url path or multiple url paths. Compares using regex, so be specific when possible. If a blacklist is supplied
, all url's will be prerendered except ones containing a blacklist path.
'''js
app.use(require('prerender-node').blacklisted('^/search'));
'''
'''js
app.use(require('prerender-node').blacklisted(['/search', '/users/.*/profile']));
'''

### beforeRender
...
```

#### <a name="apidoc.element.prerender-node.buildApiUrl"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>buildApiUrl (req)](#apidoc.element.prerender-node.buildApiUrl)
- description and source-code
```javascript
buildApiUrl = function (req) {
  var prerenderUrl = prerender.getPrerenderServiceUrl();
  var forwardSlash = prerenderUrl.indexOf('/', prerenderUrl.length - 1) !== -1 ? '' : '/';

  var protocol = req.connection.encrypted ? "https" : "http";
  if (req.headers['cf-visitor']) {
    var match = req.headers['cf-visitor'].match(/"scheme":"(http|https)"/);
    if (match) protocol = match[1];
  }
  if (req.headers['x-forwarded-proto']) {
    protocol = req.headers['x-forwarded-proto'].split(',')[0];
  }
  if (this.protocol) {
    protocol = this.protocol;
  }
  var fullUrl = protocol + "://" + (this.host || req.headers['x-forwarded-host'] || req.headers['host']) + req.url;
  return prerenderUrl + forwardSlash + fullUrl;
}
```
- example usage
```shell
...
};


prerender.prerenderServerRequestOptions = {};

prerender.getPrerenderedPageResponse = function(req, callback) {
var options = {
  uri: url.parse(prerender.buildApiUrl(req)),
  followRedirect: false,
  headers: {}
};
for (var attrname in this.prerenderServerRequestOptions) { options[attrname] = this.prerenderServerRequestOptions[attrname]; }
if (this.forwardHeaders === true) {
  Object.keys(req.headers).forEach(function(h) {
    // Forwarding the host header can cause issues with server platforms that require it to match the URL
...
```

#### <a name="apidoc.element.prerender-node.getPrerenderServiceUrl"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>getPrerenderServiceUrl ()](#apidoc.element.prerender-node.getPrerenderServiceUrl)
- description and source-code
```javascript
getPrerenderServiceUrl = function () {
  return this.prerenderServiceUrl || process.env.PRERENDER_SERVICE_URL || 'http://service.prerender.io/';
}
```
- example usage
```shell
...
  response.body = content;
  callback(null, response);
});
};


prerender.buildApiUrl = function(req) {
var prerenderUrl = prerender.getPrerenderServiceUrl();
var forwardSlash = prerenderUrl.indexOf('/', prerenderUrl.length - 1) !== -1 ? '' : '/';

var protocol = req.connection.encrypted ? "https" : "http";
if (req.headers['cf-visitor']) {
  var match = req.headers['cf-visitor'].match(/"scheme":"(http|https)"/);
  if (match) protocol = match[1];
}
...
```

#### <a name="apidoc.element.prerender-node.getPrerenderedPageResponse"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>getPrerenderedPageResponse (req, callback)](#apidoc.element.prerender-node.getPrerenderedPageResponse)
- description and source-code
```javascript
getPrerenderedPageResponse = function (req, callback) {
  var options = {
    uri: url.parse(prerender.buildApiUrl(req)),
    followRedirect: false,
    headers: {}
  };
  for (var attrname in this.prerenderServerRequestOptions) { options[attrname] = this.prerenderServerRequestOptions[attrname]; }
  if (this.forwardHeaders === true) {
    Object.keys(req.headers).forEach(function(h) {
      // Forwarding the host header can cause issues with server platforms that require it to match the URL
      if (h == 'host') {
        return;
      }
      options.headers[h] = req.headers[h];
    });
  }
  options.headers['User-Agent'] = req.headers['user-agent'];
  options.headers['Accept-Encoding'] = 'gzip';
  if(this.prerenderToken || process.env.PRERENDER_TOKEN) {
    options.headers['X-Prerender-Token'] = this.prerenderToken || process.env.PRERENDER_TOKEN;
  }

  request.get(options).on('response', function(response) {
    if(response.headers['content-encoding'] && response.headers['content-encoding'] === 'gzip') {
      prerender.gunzipResponse(response, callback);
    } else {
      prerender.plainResponse(response, callback);
    }
  }).on('error', function(err) {
    callback(err);
  });
}
```
- example usage
```shell
...
  res.writeHead(cachedRender.status || 200, {
    "Content-Type": "text/html"
  });
  return res.end(cachedRender.body || '');
}
    }

    prerender.getPrerenderedPageResponse(req, function(err, prerenderedResponse){
prerender.afterRenderFn(err, req, prerenderedResponse);

if(prerenderedResponse){
  res.writeHead(prerenderedResponse.statusCode, prerenderedResponse.headers);
  return res.end(prerenderedResponse.body);
} else {
  next(err);
...
```

#### <a name="apidoc.element.prerender-node.gunzipResponse"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>gunzipResponse (response, callback)](#apidoc.element.prerender-node.gunzipResponse)
- description and source-code
```javascript
gunzipResponse = function (response, callback) {
  var gunzip = zlib.createGunzip()
    , content = '';

  gunzip.on('data', function(chunk) {
    content += chunk;
  });
  gunzip.on('end', function() {
    response.body = content;
    delete response.headers['content-encoding'];
    delete response.headers['content-length'];
    callback(null, response);
  });
  gunzip.on('error', function(err){
    callback(err);
  });

  response.pipe(gunzip);
}
```
- example usage
```shell
...
  options.headers['Accept-Encoding'] = 'gzip';
  if(this.prerenderToken || process.env.PRERENDER_TOKEN) {
    options.headers['X-Prerender-Token'] = this.prerenderToken || process.env.PRERENDER_TOKEN;
  }

  request.get(options).on('response', function(response) {
    if(response.headers['content-encoding'] && response.headers['content-encoding'] === 'gzip') {
      prerender.gunzipResponse(response, callback);
    } else {
      prerender.plainResponse(response, callback);
    }
  }).on('error', function(err) {
    callback(err);
  });
};
...
```

#### <a name="apidoc.element.prerender-node.plainResponse"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>plainResponse (response, callback)](#apidoc.element.prerender-node.plainResponse)
- description and source-code
```javascript
plainResponse = function (response, callback) {
  var content = '';

  response.on('data', function(chunk) {
    content += chunk;
  });
  response.on('end', function() {
    response.body = content;
    callback(null, response);
  });
}
```
- example usage
```shell
...
    options.headers['X-Prerender-Token'] = this.prerenderToken || process.env.PRERENDER_TOKEN;
  }

  request.get(options).on('response', function(response) {
    if(response.headers['content-encoding'] && response.headers['content-encoding'] === 'gzip') {
      prerender.gunzipResponse(response, callback);
    } else {
      prerender.plainResponse(response, callback);
    }
  }).on('error', function(err) {
    callback(err);
  });
};

prerender.gunzipResponse = function(response, callback) {
...
```

#### <a name="apidoc.element.prerender-node.set"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>set (name, value)](#apidoc.element.prerender-node.set)
- description and source-code
```javascript
set = function (name, value) {
  this[name] = value;
  return this;
}
```
- example usage
```shell
...
'''js
app.use(require('prerender-node'));
'''

or if you have an account on [prerender.io](http://prerender.io) and want to use your token:

'''js
app.use(require('prerender-node').set('prerenderToken', 'YOUR_TOKEN'));
'''

'Note' If you're testing locally, you'll need to run the [prerender server](https://github.com/prerender/prerender) locally so that
 it has access to your server.

This middleware is tested with Express3 and Express4, but has no explicit dependency on either.

## Testing
...
```

#### <a name="apidoc.element.prerender-node.shouldShowPrerenderedPage"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>shouldShowPrerenderedPage (req)](#apidoc.element.prerender-node.shouldShowPrerenderedPage)
- description and source-code
```javascript
shouldShowPrerenderedPage = function (req) {
  var userAgent = req.headers['user-agent']
    , bufferAgent = req.headers['x-bufferbot']
    , isRequestingPrerenderedPage = false;

  if(!userAgent) return false;
  if(req.method != 'GET' && req.method != 'HEAD') return false;

  //if it contains _escaped_fragment_, show prerendered page
  var parsedQuery = url.parse(req.url, true).query;
  if(parsedQuery && parsedQuery['_escaped_fragment_'] !== undefined) isRequestingPrerenderedPage = true;

  //if it is a bot...show prerendered page
  if(prerender.crawlerUserAgents.some(function(crawlerUserAgent){ return userAgent.toLowerCase().indexOf(crawlerUserAgent.toLowerCase
()) !== -1;})) isRequestingPrerenderedPage = true;

  //if it is BufferBot...show prerendered page
  if(bufferAgent) isRequestingPrerenderedPage = true;

  //if it is a bot and is requesting a resource...dont prerender
  if(prerender.extensionsToIgnore.some(function(extension){return req.url.toLowerCase().indexOf(extension) !== -1;})) return false
;

  //if it is a bot and not requesting a resource and is not whitelisted...dont prerender
  if(Array.isArray(this.whitelist) && this.whitelist.every(function(whitelisted){return (new RegExp(whitelisted)).test(req.url) ===
false;})) return false;

  //if it is a bot and not requesting a resource and is not blacklisted(url or referer)...dont prerender
  if(Array.isArray(this.blacklist) && this.blacklist.some(function(blacklisted){
    var blacklistedUrl = false
      , blacklistedReferer = false
      , regex = new RegExp(blacklisted);

    blacklistedUrl = regex.test(req.url) === true;
    if(req.headers['referer']) blacklistedReferer = regex.test(req.headers['referer']) === true;

    return blacklistedUrl || blacklistedReferer;
  })) return false;

  return isRequestingPrerenderedPage;
}
```
- example usage
```shell
...


var request = require('request')
  , url = require('url')
  , zlib = require('zlib');

var prerender = module.exports = function(req, res, next) {
  if(!prerender.shouldShowPrerenderedPage(req)) return next();

  prerender.beforeRenderFn(req, function(err, cachedRender) {

if (!err && cachedRender) {
  if (typeof cachedRender == 'string') {
    res.writeHead(200, {
      "Content-Type": "text/html"
...
```

#### <a name="apidoc.element.prerender-node.whitelisted"></a>[function <span class="apidocSignatureSpan">prerender-node.</span>whitelisted (whitelist)](#apidoc.element.prerender-node.whitelisted)
- description and source-code
```javascript
whitelisted = function (whitelist) {
  prerender.whitelist = typeof whitelist === 'string' ? [whitelist] : whitelist;
  return this;
}
```
- example usage
```shell
...

# Customization

### Whitelist

Whitelist a single url path or multiple url paths. Compares using regex, so be specific when possible. If a whitelist is supplied
, only urls containing a whitelist path will be prerendered.
'''js
app.use(require('prerender-node').whitelisted('^/search'));
'''
'''js
app.use(require('prerender-node').whitelisted(['/search', '/users/.*/profile']));
'''

### Blacklist
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
