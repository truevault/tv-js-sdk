# TrueVault JavaScript SDK

The official JavasScript SDK for TrueVault. For more information about TrueVault, check out our [website](https://www.truevault.com) and [API documentation](https://docs.truevault.com). To see how the SDK is used in a real application, check out the [TrueVault React Sample App](https://github.com/truevault/tv-react-js-sample-app).

_Note: This SDK is only supported for the latest release of Chrome._

## Install using unpkg CDN

Simply copy this line into your HTML:
```html
<script src="https://unpkg.com/truevault-js-sdk/build/index.js"></script>
```

## Install using yarn / npm

First download the package using yarn or npm.

```
yarn add truevault-js-sdk

// OR

npm install truevault-js-sdk
```

Then import the JS SDK into your project:

### ES6
```javascript
import TrueVaultClient from 'truevault-js-sdk';
```

### ES5
```javascript
const TrueVaultClient = require('truevault-js-sdk');
```

## Usage

Initialize a TrueVaultClient using an access token or API key

```javascript
const tvClient = new TrueVaultClient(apiKeyOrAccessToken);
```

You can also create a new TrueVaultClient by logging in:

```javascript
const tvClient = await TrueVaultClient.login(accountId, username, password, mfaCode);
```

### Asynchronous Requests

The methods in this SDK make asynchronous web requests to TrueVault and return Promises. We recommend using async/await in favor of Promises wherever possible for clarity and conciseness.

#### async/await
```javascript
async readTrueVaultDocument() {
    try {
        const response = await tvClient.readDocument(vaultId, documentId);
        console.log(response);
    } catch (err) {
        console.error(err);
    }
}
```

#### Promises
```javascript
readTrueVaultDocument() {
    tvClient.readDocument(vaultId, documentId).then(response => {
        console.log(response);
    }).catch(err => {
        console.error(err);
    });
}
```

### Example

Test out the SDK with this simple [JSFiddle](https://jsfiddle.net/TrueVault/wq4em2m1/) example.

## Development

Make changes to `index.js` and then bundle them into `build/index.js` with webpack:

`./node_modules/.bin/webpack`

## License

This SDK is released under the [BSD 3-Clause License](LICENSE).
