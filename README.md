# OpenRPC Generator: Client

<center>
  <span>
    <img alt="CircleCI branch" src="https://img.shields.io/circleci/project/github/open-rpc/generator-client/master.svg">
    <img src="https://codecov.io/gh/open-rpc/generator-client/branch/master/graph/badge.svg" />
    <img alt="Dependabot status" src="https://api.dependabot.com/badges/status?host=github&repo=open-rpc/generator-client" />
    <img alt="Chat on Discord" src="https://img.shields.io/badge/chat-on%20discord-7289da.svg" />
    <img alt="npm" src="https://img.shields.io/npm/dt/@open-rpc/generator-client.svg" />
    <img alt="GitHub release" src="https://img.shields.io/github/release/open-rpc/generator-client.svg" />
    <img alt="GitHub commits since latest release" src="https://img.shields.io/github/commits-since/open-rpc/generator-client/latest.svg" />
    <img alt="js badge" src="https://img.shields.io/badge/js-javascript-yellow.svg" />
    <img alt="rs badge" src="https://img.shields.io/badge/rs-rust-brown.svg" />
  </span>
</center>


Multi-language client generator tool for [open-rpc](https://github.com/open-rpc/spec) APIs. Developers generate a client by passing an OpenRPC Document to _this_ tool which generates a client based on the supported language templates.

![overview diagram](https://github.com/open-rpc/design/blob/master/diagrams/generator-client/open-rpc-diagrams.png?raw=true)

Supported client languages:

## Install

```shell
npm install -g @open-rpc/generator-client
```

Check install or update package

```shell
open-rpc-generator-client --version

npm -g update @open-rpc/generator-client
```

## Usage

### Generating a Client

```shell
open-rpc-generator-client \
  -s https://raw.githubusercontent.com/open-rpc/examples/master/service-descriptions/petstore-openrpc.json \
  PetStore
```

Using the `open-rpc-generator-client` command, then passing an example OpenRPC document `petstore-openrpc.json` in the directory of `Petstore`.

### Using Docker ![docker-icon](https://github.com/open-rpc/design/blob/master/png/docker-icon-16x.png?raw=true)

In action (for a js client):

```shell
docker run \
  -v $(pwd)/petstore/:/petstore \
  openrpc/generator-client \
    -s https://raw.githubusercontent.com/open-rpc/examples/master/service-descriptions/petstore-openrpc.json
    petstore
```

## Examples

The [examples](https://github.com/open-rpc/examples/tree/master/service-descriptions) repository contains example open-rpc documents.

Petstore example: https://raw.githubusercontent.com/open-rpc/examples/master/service-descriptions/petstore-openrpc.json

![petstore-generated](https://github.com/stevanlohja/design/blob/master/videos-gifs/generator-client/001-generate-client-demo/001-generate-client-demo.gif?raw=true)

When a client is generated `cd` in the directory and `ls` to view the contents.

```shell
$ ls
rs ts
```

The generator client tool creates the client directories by language. E.i: `rs/` for generated Rust client and `ts` for generated Typescript (JavaScript) client. A developer can choose which client language they want to use from here.

## Resources

- [@open-rpc/generator-client package](https://www.npmjs.com/package/@open-rpc/generator-client)
- [example open-rpc documents](https://github.com/open-rpc/examples/tree/master/service-descriptions)
