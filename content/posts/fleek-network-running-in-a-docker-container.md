---
template: post
draft: false
title: 'Fleek Network: Running in a Docker container'
slug: fleek-network-running-in-a-docker-container
date: 2022-12-05T23:00:00Z
canonical: ''
description: A guide on how to run Fleek Network in a docker container
category: Tutorial
tags:
- DCDN
- Guide
- Getting Started
- Fleek Network
- Docker

---

# Fleek Network: Running in a Docker container

Our Docker image provides all the requirements to have Fleek Network running quickly. The following guide will provide you a quick reference to get you started!

If you need to deep dive into Docker, check the oficial getting started [here](https://docs.docker.com/get-started/).

## Install Docker desktop

The simplest way to run docker is to visit the https://www.docker.com/, download and install Docker Desktop.

💡 Some users might prefer to look into the Docker daemon (dockerd), in that case check the [docs](https://docs.docker.com), as we're trying to keep it simple here!

Once Docker desktop is installed, you should start or open the application in your operating system! 

Also, you'll be able to run it via the CLI, as such:

```sh
docker -v
```
```
Docker version 20.10.6, build 370c289
```

Make sure that you can run the command above in your terminal, as that hints everything's ok to go!

## Build the Docker image

We are assuming that you've followed our [Fleek Network: Getting started guide](https://blog.fleek.co/posts/fleek-network-getting-started-guide) and have successfully cloned the `ursa` repository, this because at time of writing the [Dockerfile](https://github.com/fleek-network/ursa/blob/32928e78afa0bbed8241ddc4d7e2456752456fd6/Dockerfile) is located in the Ursa repository, [here](https://github.com/fleek-network/ursa/blob/32928e78afa0bbed8241ddc4d7e2456752456fd6/Dockerfile). Also, the image builder requires the source files to build on.

If you have cloned the project correctly, you should `change directory` to the project root directory.

At time of writing, this is how the project root looks like:

```sh
.
├── Cargo.toml
├── Dockerfile
├── Makefile
├── README.md
├── crates
├── infra
├── rust-toolchain.toml
└── specs
```

Make sure that your work directory is set to the project root to build the Docker image from the [Dockerfile](https://github.com/fleek-network/ursa/blob/32928e78afa0bbed8241ddc4d7e2456752456fd6/Dockerfile) and when ready, run the Docker build command:

```sh
docker build -t ursa -f ./Dockerfile .
```

The build process takes awhile and you have to wait for completion. The output should be similar to:

```
[+] Building 16.1s (8/16)                                                                                                                           
 => [internal] load build context                                                                                                              0.2s
 => => transferring context: 12.95MB                                                                                                           0.2s
 => [builder 1/6] FROM docker.io/library/rust:latest@sha256:6d44ed87fe759752c89d1f68596f84a23493d3d3395ed843d3a1c104866e5d9e                  13.5s
 => => resolve docker.io/library/rust:latest@sha256:6d44ed87fe759752c89d1f68596f84a23493d3d3395ed843d3a1c104866e5d9e                           0.0s
 => => sha256:6d44ed87fe759752c89d1f68596f84a23493d3d3395ed843d3a1c104866e5d9e 988B / 988B                                                     0.0s
 => => sha256:6c20d87766142d058f3e21874fe1db426c49ce3e1575c8c300fdc27d06db92a9 1.59kB / 1.59kB                                                 0.0s
 => => sha256:c85a0be79bfba309d1f05dc40b447aa82b604593531fed1e7e12e4bef63483a5 10.88MB / 10.88MB                                              10.1s
 => => sha256:c7bf205db148c9f9202dbece143e86487c678d108c3936897cfd9bcd7915dd3c 6.42kB / 6.42kB                                                 0.0s
 ```

⚠️ The Docker image is only required to be built once and on every remote repository changes, versionins you might be interested in. Otherwise, you are not required to build it everytime, to run the node. Bear in mind that if you don't update your build often, you won't have the latest changes, which happen frequently with all the ongoing development! This is quite important to understand, as it causes confusion to some users.

## Run the Docker container

Once the Docker image is ready, you can run it by providing a container and image name!

Since we want to interact with the process `ursa`, we'll run in interactive mode by using the flags `-it`.

```sh
docker run -p 4069:4069 --name ursa-cli -it ursa
```

We are providing a custom name of our liking (ursa-cli) for the container and the image name we have built previously (ursa).

```sh
docker run -p <HOST-PORT>:<CONTAINER-PORT> --name <CONTAINER-NAME> -it <IMAGE>
```

💡 We understand these commands might be hard to remember and provide some utility commands for your convenience. Although, if you need naming, port customisation, then you can stick with the knowledge you've acquired, or use this document as a reference. The utility commands require [make](https://www.gnu.org/software/make/manual/make.html), most operating systems have it installed by default, otherwise you can use a web search engine to find instructions on how to install it in your operating system.

The utility commands are the `docker-build` and `docker-run`.

Respectively, execute `docker-build` to build the Docker image:

```sh
make docker-build
```

Execute the `docker-run` to run the Docker container based in the built image:

```sh
make docker-run
```

Remember, the utility commands will use default naming and port numbers. Use the original Docker commands for better control or customisation.

If all goes well, the output should be similar to:

```sh
2022-12-05T17:06:25.943684Z  INFO ursa: UrsaConfig: UrsaConfig { mdns: false, relay_server: true, autonat: true, relay_client: true, swarm_addr: "/ip4/0.0.0.0/tcp/6009", bootstrap_nodes: ["/ip4/159.223.211.234/tcp/6009/p2p/12D3KooWDji7xMLia6GAsyr4oiEFD2dd3zSryqNhfxU3Grzs1r9p", "/ip4/146.190.232.131/tcp/6009/p2p/12D3KooWGw8vCj9XayJDMXUiox6pCUFm7oVuWkDJeE2H9SDQVEcM"], database_path: Some("ursa_db"), identity: "default", keystore_path: "/root/.config/ursa/keystore" }
2022-12-05T17:06:25.944223Z ERROR ursa::ursa::identity: Failed to load identity `No such file or directory (os error 2)`
2022-12-05T17:06:25.946079Z  INFO ursa::ursa::identity: Created identity `default` (12D3KooWRis5Gn8TrKNyvx5iizTMKqVyJehw2KRSRAR79FMnxLqQ)
2022-12-05T17:06:25.946119Z  INFO ursa: Using ursa_db as database path
2022-12-05T17:06:25.974520Z  INFO ursa_network::discovery: Bootstrapping with [(PeerId("12D3KooWDji7xMLia6GAsyr4oiEFD2dd3zSryqNhfxU3Grzs1r9p"), "/ip4/159.223.211.234/tcp/6009"), (PeerId("12D3KooWGw8vCj9XayJDMXUiox6pCUFm7oVuWkDJeE2H9SDQVEcM"), "/ip4/146.190.232.131/tcp/6009")]
2022-12-05T17:06:25.975579Z  INFO ursa_rpc_server::server: Server (Rpc and http) starting up
2022-12-05T17:06:25.975618Z  INFO ursa_index_provider::provider: index provider starting up
2022-12-05T17:06:25.975632Z  INFO ursa_rpc_server::server: listening on 0.0.0.0:4069
2022-12-05T17:06:25.975806Z  INFO ursa_index_provider::provider: index provider listening on: 0.0.0.0:8070
2022-12-05T17:06:25.975553Z  INFO ursa_network::service: Node starting up with peerId PeerId("12D3KooWRis5Gn8TrKNyvx5iizTMKqVyJehw2KRSRAR79FMnxLqQ")
2022-12-05T17:06:25.975885Z  INFO ursa_metrics::metrics: listening on 0.0.0.0:4070
```

A few points to notice are the listener port number and hostname. As described in the [Run the Docker container](#run-the-docker-container), the container listener port number is exposed to your host's port number.

Here's an example of a curl request for the http headers, as a quick healthcheck.

```sh
curl -I 127.0.0.1:4069
```

For users who need high customisation, the Docker port binding is an important concept to understand when working with containers. For example, we can extend the previous `p` by providing.

```sh
-p <HOST-ADDRESS>:<CONTAINER-PORT>:<HOST-PORT>
```

## Stop the Docker container

After you're done with the process, the Docker container can be stopped by:

```sh
docker stop <CONTAINER-NAME>
```

In our case, we'd like to stop `ursa-cli`:

```sh
docker stop ursa-cli
```

## Re-run the Docker container

## Delete the Docker container

The Docker container can be removed by:

```sh
docker rm <CONTAINER-NAME>
```

For what matters to us, we'd like to delete `ursa-cli`:

```sh
docker rm ursa-cli
```

When we delete a container, it's no longer available and thus we'd have to 

## 

Start the bash shell in the container:

```sh
docker exec -it <CONTAINER-NAME> bash
```

As we have `ursa-cli` for our container name example, do:

```sh
docker exec -it ursa-cli bash
```

Here, we're just looking into how to execute a process in the container where host and port binding is still relevant and required to be applied, if you haven't, otherwise your host will not have the correct bindings. Bear in mind that Docker executes a process in the container, not your host!

For example, we could then check the `help` flag.

```sh
/ursa --help
```

```sh
CLI options

USAGE:
    ursa [FLAGS] [OPTIONS] [SUBCOMMAND]

FLAGS:
    -h, --help       Prints help information
    -r, --rpc        Allow rpc to be active or not (default = true)
    -V, --version    Prints version information

OPTIONS:
    -c, --config <config>                  A toml file containing relevant configurations
    -d, --database-path <database-path>    Database path where store data
    -i, --identity <identity>              Identity name. If not provided, a default identity will be created and reused
                                           automatically
    -k, --keystore-path <keystore-path>    Path to the keystore directory. Defaults to ~/.config/ursa/keystore
    -r, --rpc-port <rpc-port>              Port used for JSON-RPC communication

SUBCOMMANDS:
    help    Prints this message or the help of the given subcommand(s)
    rpc     run rpc commands from cli
```

💡 At time of writing the Docker build places the ursa binary in the pathname `/`, thus we executed `/ursa --help`, if you wonder where the forward slash is used for. You can add the the directory to the system PATH but we should tweak the Docker file shortly and `ursa` available globally in the container.
