# Protobuf test

## Demo

[https://theremix.github.io/protobuf-test](https://theremix.github.io/protobuf-test)

## Goal

Load [./src/proto/hello.js](./src/proto/hello.js) in this app, encode any message, and print the `bytes`

the trick is, use this svelte setup (rollup) and configure it in some way to load a protobuf library that can encode/decode.

There are two major libraries, [official google (protoc)](https://developers.google.com/protocol-buffers/docs/reference/javascript-generated) and [protobufjs (pbjs)](https://www.npmjs.com/package/protobufjs)

use any library that can encode/decode protobuf syntax version 3, it doesn't have to be the ones listed


## Proof of Concept

```sh
npm i
npm run compile-proto
npm run dev
```
