# DEVELOPERS GUIDE

[![Build Status](https://travis-ci.org/kenigbolo/network-speed.png)](https://travis-ci.org/kenigbolo/network-speed)
[![](https://data.jsdelivr.com/v1/package/npm/network-speed/badge)](https://www.jsdelivr.com/package/npm/network-speed)

## Getting Started

- Clone the application with
  `git clone https://github.com/kenigbolo/network-speed.git` or use ssh
  `git clone git@github.com:kenigbolo/network-speed.git`.

## Dependencies

- NPM 6.6

## Description

Basic Javascript Module used to check upload and download speed. Contributions
are welcome.

## NPM

This package has been published on
[NPM](https://www.npmjs.com/package/network-speed) and is freely available
according to the MIT license. To install via npm simply run
`npm install network-speed`.

## Usage

```javascript
const NetworkSpeed = require('network-speed');
const testNetworkSpeed = new NetworkSpeed();

getNetworkDownloadSpeed();

async function getNetworkDownloadSpeed() {
  const baseUrl = 'http://eu.httpbin.org/stream-bytes/50000000';
  const fileSize = 500000;
  const speed = await testNetworkSpeed.checkDownloadSpeed(baseUrl, fileSize);
  console.log(speed);
}

getNetworkUploadSpeed();

async function getNetworkUploadSpeed() {
  const options = {
    hostname: 'www.google.com',
    port: 80,
    path: '/catchers/544b09b4599c1d0200000289',
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
  };
  const speed = await testNetworkSpeed.checkUploadSpeed(options);
  console.log(speed);
}
```

## StandAlone

running `npm start` will trigger the test usage file to run and calculate your
upload/download speed `See the test usage file`
