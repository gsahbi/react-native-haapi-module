
# react-native-haapi-react-native-module

## Getting started

`$ npm install @curity/haapi-react-native-module --save`

### Mostly automatic installation

`$ react-native link @curity/haapi-react-native-module`

## Usage
```javascript
import {NativeModules} from "react-native";

const {HaapiModule} = NativeModules;

// Example configuration
const haapiConfiguration = {
    "appRedirect": "app:start",
    "keyStoreAlias": "haapi-react-native",
    "clientId": "react-dev-client",
    "baseUri": "https://login.example.com",
    "tokenEndpointUri": "https://login.example.com/oauth/token",
    "authorizationEndpointUri": "https://login.example.com/oauth/authorize",
    "revocationEndpointUri": "https://login.example.com/oauth/revoke",
    "scope": "openid profile",
    "registrationEndpointUri": "https://login.example.com/oauth/registration",
    "fallback_template_id": "react-native-fallback",
    "registration_secret": "my-good-secret"
}

HaapiModule.load(haapiConfiguration)

export default HaapiModule;
```

## Example implementation

See https://github.com/curityio/haapi-react-native-example for example implementation

## Known limitations
* Selfsigned certificates needs to be imported to trust store
* No Extra authorization parameters like `acr`
* Only Android yet
