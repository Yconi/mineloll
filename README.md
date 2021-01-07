# ngrok-minecraft-server 
[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/nekkan/ngrok-minecraft-server)

A template to run a Minecraft server easily in a Linux environment. Usually used in Gitpod.

⚠️ **Do not run scripts in the `scripts` folder. Use the root folder for it, for example: `scripts/start`**

# How to use?

Use this template in a Linux environment and run the needed scripts. You may change the region for
ngrok in `scripts/host` (default: South America).

# Starting the Minecraft server

  1. Setup the environment by running the `scripts/enviroment` script.

  2. Setup the Minecraft server with the version you wish to use (Terminal #1).
  
  3. Run the `scripts/host` scripts in another terminal (Terminal #2).

# Script structure

  * `scripts/host` Expose the Minecraft server TCP services to `ngrok`.
  Needed arguments: `authtoken`. For example: `scripts/host myAuthTokenHere`

  * `scripts/move` Moves all files from `external` folder to the `server` directory.

  * `scripts/save` Commit all unstaged changes and push them to the `origin` remote (branch: `main`).

  * `scripts/setup` Download a Spigot JAR for the given version.
  Needed arguments: `version`. For example: `scripts/setup 1.16.4`

  * `scripts/start` Start the Minecraft server and saves all unstaged changes when stopping.

  * `scripts/environment` Setups all needed components other than the Minecraft server.

# Installing plugins

Create a folder called `plugins` in the `external` directory. The structure must look like this:
`external/plugins`. Drop all plugins you wish to use to the created folder then run the `move` script.

# External worlds

Delete all `world*` folders in the `server` directory then move your world folder to the `external`
directory. The strucutre must look like this: `external/world*` then you must run the `move` script.
