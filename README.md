node-dns-sync
=============

Sync/Blocking DNS resolve. Main usecase is in node server startup.

How to Use
-------

If coming from `dns-sync`, replace the entry in the package dependencies:
```json5
  "dependencies": {
    "dns-sync": "npm:@amoo-miki/dns-sync@~0.2",
    ...
  }
```

```javascript
var dnsSync = require('dns-sync');

console.log(dnsSync.resolve('www.paypal.com'));     //should return the IP address
console.log(dnsSync.resolve('www.yahoo.com'));
console.log(dnsSync.resolve('www.non-host.something')); //should return null

console.log(dnsSync.resolve('www.google.com', 'AAAA')); //should return AAAA records
console.log(dnsSync.resolve('google.com', 'NS'));   //should return NS record
```
