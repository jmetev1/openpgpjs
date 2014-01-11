OpenPGP.js
==========

[OpenPGP.js](http://openpgpjs.org/) is a Javascript implementation of the OpenPGP protocol. This is defined in [RFC 4880](http://tools.ietf.org/html/rfc4880).

[![Build Status](https://secure.travis-ci.org/openpgpjs/openpgpjs.png?branch=master,v0.1.x)](http://travis-ci.org/openpgpjs/openpgpjs)

### Node support

For server side use, install via npm:

    npm install openpgp

Example:

    var openpgp = require('openpgp');
    var key = '-----BEGIN PGP PUBLIC KEY BLOCK ... END PGP PUBLIC KEY BLOCK-----';
    var publicKey = openpgp.key.readArmored(key);
    var pgpMessage = openpgp.encryptMessage(publicKey.keys, 'Hello, World!');

### Browser support

Fetch a minified build under [releases](https://github.com/openpgpjs/openpgpjs/releases). The library can be loaded via  AMD/require.js or accessed globally via `window.openpgp`.

OpenPGP.js currently only fully supports browsers that implement `window.crypto.getRandomValues`. If you can help us support more browsers and runtimes, please chip in!

### Security recommendations

It should be noted that browser based applications, following a [**host-based security**](https://www.schneier.com/blog/archives/2012/08/cryptocat.html) model, provide users with less security than installable apps with auditable static versions. This can be achieved by deploying your HTML5 app as a [Firefox](https://developer.mozilla.org/en-US/Marketplace/Publishing/Packaged_apps) or [Chrome](http://developer.chrome.com/apps/about_apps.html) packaged app. These runtimes typically also enforce a strict [Content Security Policy (CSP)](http://www.html5rocks.com/en/tutorials/security/content-security-policy/) to protect your users against [XSS](http://en.wikipedia.org/wiki/Cross-site_scripting). This [blogpost](http://tonyarcieri.com/whats-wrong-with-webcrypto) explains the trust model of the web quite well.

It is also recommended to set a strong passphrase that protects the user's private key on disk.

## Development

You can create your own build in `dist/openpgp.min.js` to use in your project.

    npm install && grunt

### Run tests

    npm test

### Documentation

A jsdoc build of our code comments is available at [doc/index.html](http://openpgpjs.org/openpgpjs/doc/index.html). Public calls should generally be made through the OpenPGP object [doc/openpgp.html](http://openpgpjs.org/openpgpjs/doc/module-openpgp.html).

### Mailing List

You can [sign up](http://list.openpgpjs.org/) for our mailing list and ask for help there.  We've recently worked on getting our [archive up and running](http://www.mail-archive.com/list@openpgpjs.org/).

### How do I get involved?

You want to help, great! Go ahead and fork our repo, make your changes and send us a pull request.

### License

GNU Lesser General Public License (2.1). Please take a look at the [LICENSE](LICENSE) file for more information.

### Resources

Below is a collection of resources, many of these were projects that were in someway a precursor to the current OpenPGP.js project. If you'd like to add your link here, please do so in a pull request or email to the list.

* [http://www.hanewin.net/encrypt/](http://www.hanewin.net/encrypt/)
* [https://github.com/seancolyer/gmail-crypt](https://github.com/seancolyer/gmail-crypt)
* [https://github.com/mete0r/openpgp-js](https://github.com/mete0r/openpgp-js)
* [http://fitblip.github.com/JSPGP-Stuffs/](http://fitblip.github.com/JSPGP-Stuffs/)
* [http://qooxdoo.org/contrib/project/crypto](http://qooxdoo.org/contrib/project/crypto)
* [https://github.com/GPGTools/Mobile/wiki/Introduction](https://github.com/GPGTools/Mobile/wiki/Introduction)
* [http://gpg4browsers.recurity.com/](http://gpg4browsers.recurity.com/)
