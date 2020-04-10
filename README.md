# Protobuf test

## Demo

[https://theremix.github.io/protobuf-test](https://theremix.github.io/protobuf-test)

## POC

Loads [./src/proto/hello.js](./src/proto/hello.js), encode a message and print as bytes

Rollup builds stand-alone protobuf definition modules compiled with [protobufjs (pbjs)](https://www.npmjs.com/package/protobufjs)

I found problems using the [official google (protoc)](https://developers.google.com/protocol-buffers/docs/reference/javascript-generated) with rollup.


## Proof of Concept

```sh
npm i
npm run compile-proto
npm run dev
```
