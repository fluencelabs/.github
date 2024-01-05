# Fluence

Fluence is a decentralized serverless computing platform.

- [Documentation - fluence.dev](https://fluence.dev)
- [Youtube](https://www.youtube.com/channel/UC3b5eFyKRFlEMwSJ1BTjpbw)
- [Discord](https://discord.com/invite/5qSnPZKh7u)
- [Telegram](https://t.me/fluence_project)
- [Telegram (ru)](https://t.me/fluenceru)
- [Telegram Updates](https://t.me/fluencedev)

## Repositories

- [Fluence CLI](https://github.com/fluencelabs/cli) - the go-to tool for fluence developers and providers
- [Nox](https://github.com/fluencelabs/nox) - reference fluence peer implementation in rust
- [JS Client](https://github.com/fluencelabs/js-client) - client-focused fluence peer implementation for browsers and NodeJS
- [Aqua](https://github.com/fluencelabs/aqua) - choreography and workflow programming language to express distributed algorithms over fluence network
- [Aqua Lib](https://github.com/fluencelabs/aqua-lib) – Aqua Standard Library
- [AquaVM](https://github.com/fluencelabs/aquavm) - VM for compiled Aqua – Aqua Intermediate Representation (AIR) scripts, commands choreography on all fluence peers
- [Marine](https://github.com/fluencelabs/marine) - asynchronous WebAssembly runtime, serves as execution environment for functions on all fluence peers


### Fluence CLI – FCLI

> https://github.com/fluencelabs/fluence-cli

Fluence CLI is your one-stop command line interface (CLI) shop to creating, deploying, paying, running, monitoring and removing distributed services to and from the Fluence peer-to-peer network.

👉 Note that Fluence CLI is currently only available for nix systems including OSX and Windows Subsystem for Linux (WSL). Moreover, Fluence CLI installs all the required dependencies not already installed on your system including Rust.

### Nox

> https://github.com/fluencelabs/nox

Nox is the reference implementation of a Fluence Peer. It is meant to be used by Fluence Providers in on-premise and cloud environments.

Nox instances connect to each other to create the Fluence p2p network. Nox integrates Marine Runtime to host WebAssembly functions. It also integrates AquaVM to execute distributed Aqua workflows.

#### System Services

The following services are considered to be the part of the Fluence protocol, and so are distributed along with Nox:
- [Decider](https://github.com/fluencelabs/decider) - listens to the Chain RPC events, and deploys Workers to Nox. Workers is a collection of functions and cron jobs, a package for a Fluence App.
- [AquaIpfs](https://github.com/fluencelabs/aqua-ipfs) – Aqua bindings for IPFS to download & upload data.
- [Registry](https://github.com/fluencelabs/registry) - experimental and limited KV storage, focused on service discovery.

### JS Client

> https://github.com/fluencelabs/js-client

JS Client is a client-focused Fluence Peer implementation. Written in TypeScript, it is mainly used in browsers and CLIs to provide an access to the Fluence Network.

JS Client connects to a chosen Nox instance by its [Multiaddress](https://docs.libp2p.io/concepts/fundamentals/addressing/), and sends Aqua workflows to call Marine Functions.

JS Client integrates [marine-js](https://github.com/fluencelabs/marine/tree/master/marine-js) to host WebAssembly functions, it also integrates AquaVM to execute Aqua workflows.

### Aqua

> https://github.com/fluencelabs/aqua


Aqua is a programming language for expressing algorithms and workflows over a decentralised distributed p2p network.

It allows to program peer-to-peer scenarios separately from the computations on peers. Applications are turned into hostless workflows over distributed function calls, which enables various levels of decentralization: from handling by a limited set of servers to complete peer-to-peer architecture by connecting user devices directly.

### Aqua API

> https://github.com/fluencelabs/aqua-lib

Aqua Standard Library includes useful functions like [math.aqua](https://github.com/fluencelabs/aqua-lib/blob/main/math.aqua), and also describes all the protocol functions in [builtins.aqua](https://github.com/fluencelabs/aqua-lib/blob/main/builtin.aqua), [subnet.aqua](https://github.com/fluencelabs/aqua-lib/blob/main/subnet.aqua) and [workers.aqua](https://github.com/fluencelabs/aqua-lib/blob/main/workers.aqua).

The protocol functions can be called from Aqua to inspect Nox or JS Client state, or command them to do something. Lots of tools are built upon this API.

Note however, that JS Client provides most of the Aqua Standard Library, but not all of it. For example, spells and subnets are missing.

### AquaVM

> https://github.com/fluencelabs/aquavm

AquaVM executes compiled Aqua, i.e., Aqua Intermediate Representation (AIR) scripts, and plays an integral role in the implementation of the Fluence peer-to-peer compute protocol. Specifically, AquaVM allows expressing network choreography in scripts and composing distributed, peer-to-peer hosted services. Moreover, AquaVM plays a significant role in facilitating function addressability in the Fluence network.

### Marine

> https://github.com/fluencelabs/marine

Marine is a modern general purpose Wasm runtime based on the [component model](https://github.com/WebAssembly/component-model) capable of running multi-module Wasm applications, aka services, with [interface-types](https://github.com/WebAssembly/interface-types) and a [shared-nothing linking](https://training.linuxfoundation.org/blog/how-and-why-to-link-webassembly-modules/) scheme. This execution model is well suited for a variety of scenarios and especially applicable to implementations following the [entity component system](https://en.wikipedia.org/wiki/Entity_component_system) (ECS) pattern or plugin-based architectures.

[Fluence](https://fluence.network) peers, such as Fluence [Rust node](https://github.com/fluencelabs/fluence), include Marine to execute the hosted Wasm services composed with [Aqua](https://github.com/fluencelabs/aqua).