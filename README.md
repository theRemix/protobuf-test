# Protobuf test

The goal is to load [./src/proto/hello.js](./src/proto/hello.js) in this app, encode any message, and print the `bytes`

the trick is, use this svelte setup (rollup) and configure it in some way to load a protobuf library that can encode/decode.

There are two major libraries, [official google (protoc)](https://developers.google.com/protocol-buffers/docs/reference/javascript-generated) and [protobufjs (pbjs)](https://www.npmjs.com/package/protobufjs)

use any library that can encode/decode protobuf syntax version 3, it doesn't have to be the ones listed


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

