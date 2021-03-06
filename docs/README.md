# GRAM SDK for TON

GRAM SDK is a blockchain toolkit for [TON](ton.org)

GRAM Navigator is an app for GRAM that includes a wallet and developer tools

## Install GRAM

Using GIT:

```bash
git clone https://github.com/gram-net/gram-sdk.git
cd gram-sdk
# use sudo on Linux!
./bin/install
```

> Don't use sudo on OSX, but on Linux using 'sudo' (or running as root) is necessary. This temporary inconvenience helps things work on all Linux distros and the docker builds.

To deploy a node: `gram deploy`

Run `gram mux` to see logs

When done deploying, visit these pages:

<http://localhost:8088> for GRAM Navigator Web App

<http://localhost:8090> for GRAM SDK Documentation

<http://localhost:8084> NodeJS API / documentation

<http://localhost:8082/last> JSON Block explorer

<http://localhost:8083/last> HTML Block explorer

JSON Block explorer uses same endpoints as HTML explorer

To stop all GRAM services: `gram shutdown`

To see the list of available commands: `gram help`

To open a TApp dev console: `gram mux dev`

To see a list of TApp dev commands: `gram helpdev`

To start Navigator in dev mode: `cd navigator && yarn start`

[TApp Developer Reference](./reference/TApp-Development.md)

## Docker

Docker is not required, but is highly recommended.

> Make sure you allocate enough RAM to Docker.

> You should reboot after installing Docker.

[Docker Ubuntu Install](./reference/docker-install-ubuntu.md).

[Docker OSX Install](https://docs.docker.com/docker-for-mac/install/).

## Validator Disk space requirements

* SANDBOX: 100GB
* TESTNET: 500GB
* MAINNET: 1TB+

## Firewall Ports

You can configure these ports by editing `gram/etc/lib/defaultenv.sh` and either running `gram env` or choosing to update your env from `gram deploy`

```bash
#Always open:
GRAM_API_PORT=8084
NAV_PORT=8088

#Only if running a node:
TON_ENGINE_OUTGOING=3278, 3278/udp
TON_ENGINE_PORT=6302, 6302/udp
CONSOLE_PORT=6303
LITESERVER_PORT=6304
JSON_EXPLORER_PORT=8082
WEB_EXPLORER_PORT=8083
```

[Docker Developer Reference](./validator-node-admin/docker.md)

[AWS Admin Reference](./reference/aws.md)

[TMUX Guide](./reference/tmux.md)

____

## Technology used by GRAM

GRAM uses [TON Technology](http://ton.org)

* GRAM SDK
  * Docker
  * Emscripten: ASM/WASM
  * NodeJS/N**: Tooling / Orchestration
* GRAM Navigator
  * Cordova: HTML5 mobile app SDK  
  * Typescript: Static typing for JS
  * Yarn: package manager
  * Electron: Desktop app
  * Vue: JS framework
    * VueX
    * vue-cli
  * Webpack: App bundler
  * Babel: JS transpiler
  * Nightwatch: End to end test framework
  * Jest: JS test framework
  * ESLint: JS syntax checker
  * SASS: CSS scripting
  * xCode iOS SDK
  * Android SDK
  * tdlib: Telegram SDK
  * Airgram: tdlib bridge API
* GRAM Bots
  * Amazon Lambda/S3
* Development Tools
  * Visual Studio Code: IDE
  * Sourcetree: GIT GUI
  * GitLab: Continuous Integration/Delivery
* Communication Tools
  * Github: Public code repository and issue tracker
  * Mattermost: Community collaboration platform
  * Telegram Messenger XD
  * MeisterTask: Kanban
