# biscuit
## A brand new bleeding edge non bloated Discord library


### Install
```sh
npm install @oasisjs/biscuit
```
> or via [cdn](dummy link)

The biscuit Discord library is built ontop of Discordeno and webspec APIs, we aim to provide portability.

### Most importantly, biscuit is:
* A modular [Discordeno](https://github.com/discordeno/discordeno) fork
* A framework to build Discord bots 
* A bleeding edge API to contact Discord

Biscuit is primarly inspired by Discord.js and Discordeno but it does not include a cache layer by default, we believe that you should not make software that does things it is not supposed to do.

### Why biscuit?:
* [Minimal](https://en.wikipedia.org/wiki/Unix_philosophy), non feature-rich!
* Crossplatform
* Consistent
* Performant

### Example bot (TS/JS)
```js
import { GatewayIntents, Session } from "biscuit";

const token = "your token goes here";

const intents = GatewayIntents.MessageContent | GatewayIntents.Guilds | GatewayIntents.GuildMessages; 
const session = new Session({ token, intents });

session.on("ready", ({ user }) => {
    console.log("Logged in as:", user.username);
});

session.on("messageCreate", (message) => {
    if (message.content.startsWith("!ping")) {
        message.reply({ content: "pong!" });
    }
});

session.start();
```

### Mininal style guide
* 4 spaces, no tabs
* Semi-colons are mandatory
* Run `deno fmt`
* Avoid circular dependencies

### Contrib guide
* Install Deno extension [here](https://marketplace.visualstudio.com/items?itemName=denoland.vscode-deno)
* Run `deno check` to make sure the library works
* Avoid sharing state between classes
