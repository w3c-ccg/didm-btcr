
# BTCR DID References (Authoritative and up-to-date)

## Documentation

* [BTCR Resolver](https://github.com/WebOfTrustInfo/rebooting-the-web-of-trust-spring2018/blob/master/final-documents/btcr-resolver.md)
* [BTCR-DID-Tests](https://github.com/w3c-ccg/did-hackathon-2018/blob/master/BTCR-DID-Tests.md) — A number of testnet registered DIDs, along with sample valid DID Documents, some unrevoked, others rotated, others revoked, along with signed verifiable claims using those DIDs
* [BTCR Playground Use Cases](https://github.com/w3c-ccg/did-hackathon-2018/blob/master/playground-goals.md)


## Playgrounds

* [btcr-tx-playground](https://weboftrustinfo.github.io/btcr-tx-playground.github.io/) - HTML/JS playground using the [btcr-did-tools-js](https://github.com/WebOfTrustInfo/btcr-did-tools-js) library
    * [Source](https://github.com/WebOfTrustInfo/btcr-tx-playground.github.io)
* [BTCR-Electron](https://github.com/AnthonyRonning/btcr-electron) - Electron playground for the btcr-did-js library.

## BTCR REST Service

Golang service that talks to btcd and provides some endpoints to help experiment with DID creation and resolution.

The service is at https://btcr-service.opdup.com (/ is a 404) and the repo is at https://github.com/kulpreet/btcr-service

### Endpoints

All endpoints return JSON objects, content-type as application/json

1. `/txref/:query/decode`
Returns a decoded txref passed as query, e.g. https://btcr-service.opdup.com/txref/txtest1:x705-jzv2-qqaz-7vuz/decode

2. `/txref/:query/txid`
Returns a txid and the utxo index for txref passed as query, e.g. https://btcr-service.opdup.com/txref/txtest1:x705-jzv2-qqaz-7vuz/txid

3. `/tx/:query`
Returns the decoded transaction for the transaction hash passed as query, e.g. https://btcr-service.opdup.com/tx/80871cf043c1d96f3d716f5bc02daa15a5e534b2a00e81a530fb40aa07ceceb6

4. `/addr/:query/spends`
Returns all the transactions associated with the address (limited to 100 for now), in reverse chronological order, for example, https://btcr-service.opdup.com/addr/mqkvMtYfTufj3iEXjYHmnopZrsowMFxrKw/spends


## Libraries

* TXREF Conversion Libraries
    * [txref-conversion-js](https://github.com/WebOfTrustInfo/txref-conversion-js) - Node.js txref conversion library; supports txref-ext
    * [txref-conversion-java](https://github.com/WebOfTrustInfo/txref-conversion-java) - Java txref conversion library; supports txref-ext
    * [txref-conversion-golang](https://github.com/kulpreet/txref) - Golang txref conversion library
    * [txref-conversion-python](https://github.com/WebOfTrustInfo/txref-conversion-python) - Python txref conversion library
* BTCR Creation/Resolution Libraries
    * [btcr-did-tools-js](https://github.com/WebOfTrustInfo/btcr-did-tools-js) - Node.js library for creating/resolving BTCR DIDs. Has browserify scripts for running in browser
    * [btcr-service](https://github.com/kulpreet/btcr-service) - A service in Go for encoding/decoding TxRefs and searching all transactions related to an address (/addr/<addr>/spends endpoint). Also, DID resolution for the simplest case of unrevoked, unrotated keys is currently in progress (/txref/<txref>/resolve). The service is live at [https://btcr-service.opdup.com/txref/txtest1:x705-jzv2-qqaz-7vuz/txid](https://btcr-service.opdup.com/txref/txtest1:x705-jzv2-qqaz-7vuz/txid). Repo [README](https://github.com/kulpreet/btcr-service/blob/master/README.md) describes the service endpoints.
    * [universal-resolver](https://github.com/decentralized-identity/universal-resolver/tree/master/implementations/java) includes [driver-did-btcr](https://github.com/decentralized-identity/universal-resolver/tree/master/implementations/java/driver-did-btcr), sample deployment is [here](https://uniresolver.io/).

## Various Introductory Material

* [Visualization of how BTCR works](https://www.icloud.com/keynote/0Bcwqiyw6RGvMZgDyFt-prI_g#BTCR)
* [BTCR DIDs and DDOs - may be out of date](https://github.com/WebOfTrustInfo/rebooting-the-web-of-trust-fall2017/blob/master/topics-and-advance-readings/btcr-dids-ddos.md)
