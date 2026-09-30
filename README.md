[![shield to Agar.io Private Servers guild](https://discordapp.com/api/guilds/407210435721560065/embed.png?style=shield)](https://discord.gg/XcKgShT)

# OgarII WebSockets Edition

Your friendly agar.io private server recreation, now using WebSockets instead of uWebSockets. Original OgarII by Luka [here](https://github.com/Luka967/OgarII)!

- It supports all current agar.io protocol versions.

- It supports handling multiple worlds, all within one instance. Be wary that you can still use up the one CPU core node.js is running on.

- It has a minimal memory footprint, and strictly uses WebSockets for networking.

- The code uses JSDoc to specify types. Understanding what the code does is down to your understanding of English.

## Notes

- Ask all your questions over on the [Agar.io Private Servers](https://discord.gg/66X2ESb) Discord guild.

- Before connecting from agar.io you will need to do `core.disableIntegrityChecks(true)` in the console.

## Running

1. Make sure you have node.js version 8 or greater.

2. Clone / [download](https://github.com/FlushDesert22/OgarII_WebSockets_Edition/archive/master.zip) the repo.

3. `npm install` in `/`.

4. `cd ./cli/`

5. `node index.js`

## Configuring

- After your first run, OgarII will drop two files in `cli/` / working directory: `log-settings.json` and `settings.json`.

- To change how OgarII runs, modify `cli/settings.json`.

- To change what gets logged, modify `cli/log-settings.json`.

## Expanding

- To create your own commands, check out `src/commands/CommandList.js` on the command API. To add it to the CLI use `ServerHandle.commands.register`, and for chat commands use `ServerHandle.chatCommands.register`.

- To create your own gamemodes, inherit `src/Gamemode.js`'s `Gamemode` abstract class, modify event handling to your wish, then add it with `ServerHandle.gamemodes.register` before the handle starts.

- The `ServerHandle` class is standalone, which means that you can completely ditch the `cli/` folder, `require("./src/ServerHandle.js")` and do whatever you want with it. OgarII is also available as an npm package for this exact purpose.
