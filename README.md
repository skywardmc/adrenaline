<div align="center">
  <a href="https://github.com/intergrav/Adrenaline">
    <img src="https://raw.githubusercontent.com/intergrav/Branding/main/adrenaline/adrenaline_textlogo_256h.png" alt="Logo" height="90">
  </a>
  <br />
  <br />
  <p align="center">
    Leading, lightweight, and unbiased performance modpack with no QoL features
    <br />
    <a href="https://github.com/intergrav/Adrenaline/wiki">Explore the wiki</a>
    ·
    <a href="https://github.com/intergrav/Adrenaline/issues">Report Bugs</a>
    ·
    <a href="https://github.com/intergrav/Adrenaline/issues">Request Features</a>
  </p>
  <a href="https://modrinth.com/modpack/adrenaline"><img src="https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/available/modrinth_vector.svg" alt="Available on Modrinth"></a>
  <a href="https://discord.gg/36Tv44cYte"><img src="https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/social/discord-singular_vector.svg" alt="Chat on Discord"></a>
  <a href="https://gitpod.io/from-referrer/"><img src="https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/supported/gitpod_vector.svg" alt="Ready for Gitpod"></a>
</div>

Adrenaline is a **client-side** or **server-side** modpack comprised of the **best combination of mods** (e.g. Sodium and Lithium, along with many more) that significantly improves rendering performance, logic performance, memory usage, and more - all without compromising on the game's vanilla looks and features! It is designed to be simple and not include any quality-of-life mods, along with not including redundant performance mods. Because of this simplicity, the modpack is compatible with a very wide range of devices and can be updated to the latest versions very quickly. Want more features? No problem! Adrenaline serves as a great foundation for performance - simply add your favorite mods on top.

For the list of mods that are included, see this [wiki page](https://github.com/skywardmc/adrenaline/wiki/Performance-features). Adrenaline can be installed on both clients and servers, so this list tells you what is installed depending on the environment.

# 📥 Installation Guide

**Please be sure to read Sodium's [Driver Compatibility](https://github.com/CaffeineMC/sodium-fabric/wiki/Driver-Compatibility) section on the wiki before installing Adrenaline. It contains some important instructions on preventing crashes and other performance issues.**

If you would like to install the modpack, go to this page on [the SkywardMC website](https://skywardmc.org/adrenaline). You can install the modpack with a third party launcher or our standalone installer. After you install, you can figure out how to tweak things to give greater optimizations in the [post-install](https://github.com/intergrav/Adrenaline/wiki/Post-install) section of the wiki. This includes procedures such as increasing your allocated memory and tweaking your game settings for your device.

After installing the modpack, you can easily add your favorite mods so long as they are compatible with the Minecraft version you are playing on. The wiki also has some recommendations on possibly improving performance further with other mods that are not suitable to be included in Adrenaline by default.

<details>

<summary>Installing Adrenaline on a server</summary>

Adrenaline also optionally functions server-side! We now use Modrinth's mrpack environment feature to install the proper mods for the correct environment. Client-side mods that are part of Adrenaline will not be installed through these methods. The server portion of this modpack was previously known as [Adrenaserver](https://modrinth.com/modpack/adrenaserver).

<details>
<summary>
📦 Install using mrpack-install
</summary>

Download `mrpack-install` through [GitHub releases](https://github.com/nothub/mrpack-install/releases) (or your distro's package if it has one) and take a look at the commands on the [README](https://github.com/nothub/mrpack-install). In Adrenaline's case, to install in your server you would run:

```sh
mrpack-install adrenaline [optional version number]
```

</details>

<details>
<summary>
🐋 Install using Docker Compose
</summary>

> It's a good idea to have some knowledge on using Docker before doing this.

1. Make sure you have Docker Engine installed properly according to the [Docker docs](https://docs.docker.com/engine/install)
2. Create a new directory
3. Place the contents below in a file called `docker-compose.yml`. This Compose file also contains some other server tweaks meant for performance, such as disabling `sync-chunk-writes`, reducing render and simulation distance, and more
4. Run `docker compose up -d` in that directory

For any other information, you can read through the [Docker Minecraft Server documentation](https://docker-minecraft-server.readthedocs.io).

```yaml
services:
  mc:
    image: itzg/minecraft-server
    tty: true
    stdin_open: true
    ports:
      - "25565:25565"
    environment:
      EULA: "TRUE"
      # Adrenaline and other mods
      MOD_PLATFORM: MODRINTH
      MODRINTH_DOWNLOAD_DEPENDENCIES: required
      MODRINTH_MODPACK: adrenaline # this installs the latest version of Adrenaline, you can also use a specific MR link to a version
      MODRINTH_PROJECTS: spark, chunky # comma separated list of extra mods
      # Server properties
      VIEW_DISTANCE: 8
      SIMULATION_DISTANCE: 5
      SYNC_CHUNK_WRITES: false # having this set to false will significantly improve performance but may cause desync issues and (extremely rare) data corruption. set to true if you don't have a backup system
    volumes:
      # Attach the relative directory 'data' to the container's /data path
      - ./data:/data
```

</details>

<details>
<summary>
✨ Install using mcman
</summary>

[mcman](https://github.com/ParadigmMC/mcman) is a tool for managing the mods/plugins/configurations of a Minecraft server. First, install mcman from [releases](https://github.com/ParadigmMC/mcman/releases). To import Adrenaline while initializing a server, use this command:

```sh
mcman init --mrpack mr:adrenaline
```

After initializing and importing the mrpack, run `mcman build` to build the server into the `server/` directory, from which you can call `cd server && sh start.sh` or `cd server && call start.bat`. For more information, check out [mcman's docs](https://github.com/ParadigmMC/mcman/blob/main/DOCS.md).

</details>

<details>
<summary>
💿 Install using mrpack4server
</summary>

See the [mrpack4server](https://github.com/Patbox/mrpack4server) Git repository for installation info. `modpack-info.json`:

```json
{
	"project_id": "adrenaline",
	"version_id": "version id or name"
}
```

</details>

<details>
<summary>
🧙 Install using packwiz-installer
</summary>

> Before doing any of this, be sure to have a backup of the server in case anything goes wrong.

[packwiz-installer](https://github.com/packwiz/packwiz-installer) is a useful tool that lets you automatically install and update a modpack through the `pack.toml` file of that pack.

Some server hosts may let you set a command that runs before the server actually starts. It's called a pre-launch command. I can't exactly help if you are using an external server provider as many don't support pre-launch commands or require you to supply your own jar file that will run the command.

First, you need to install `packwiz-installer-bootstrap` from [here](https://github.com/packwiz/packwiz-installer-bootstrap/releases). After that, move it to the same folder as your server's Fabric loader jar. This will usually be the root of the server.

You may change the MC version of the modpack ([available versions only](https://github.com/intergrav/adrenaline/tree/main/versions)).

```sh
java -jar packwiz-installer-bootstrap.jar -g -s server https://raw.githack.com/intergrav/Adrenaline/main/versions/fabric/1.21.1/pack.toml
```

If you are running this server through a batch file or shell script, you can add this command before your server's launch command and it should work just fine.

_Having trouble? Check out the [packwiz wiki](https://packwiz.infra.link/tutorials/installing/packwiz-installer/#using-a-modpack-with-a-server) and, if that doesn't help, ask in the [packwiz Discord server](https://discord.gg/DcSkRF4)._

</details>

</details>

# ⭐ Features

### 🚀 Major performance improvement

Adrenaline aims to significantly improve rendering and game logic performance, along with memory and hardware usage, without compromising on the game's looks or features in any way. This is done with various optimization mods that are actively tested for stability and improvement. Some mods are also pre-configured. Adrenaline wouldn't exist without projects like [Sodium](https://modrinth.com/mod/sodium), so I advise you to donate to mod authors and contributors if you can.

For the list of performance mods that are included, see this [wiki page](https://github.com/skywardmc/adrenaline/wiki/Performance-features). Adrenaline can be installed on both clients and servers, so this list tells you what is installed depending on the environment.

### 🪶 Lightweight

I only pick the combination of mods that work best with eachother, and don't include performance mods that aren't necessary or often break compatibility with other mods or device hardware. I also don't include any quality of life mods in the pack for the sole purpose of keeping it simple and flexible. This simplicity allows you to very easily build your own modpacks based on Adrenaline, or simply install Adrenaline and play with your favorite mods.

### ⚙️ Source-available

All mods in Adrenaline are either open-source or source-available, which means you can view the code of mods and see exactly what they are doing. Adrenaline is also available as [packwiz projects on GitHub](https://github.com/skywardmc/adrenaline) so that you can easily view what's being changed, contribute if you would like to, or fork the modpack to create your own project. If you would like to view the mods shipped with Adrenaline, simply look at the dependencies in the Modrinth page or look in the Git repository.

# ✅ Hardware Compatibility

For Hardware Compatibility information, see the corresponding section in [Sodium's Modrinth description](https://modrinth.com/mod/sodium#hardware-compatibility).

# 🐛 How to Report Issues

Experiencing bugs, crashes, or other issues? Feel free to open an issue on the [issue tracker](https://github.com/intergrav/Adrenaline/issues). Be sure to include necessary information like your hardware/software (e.g. GPU and CPU, modpack version and OS) so that it's easier for us to find issues and resolve them.

# ❓ Frequently Asked Questions

For a few frequently asked questions, along with tons of other information, consider visiting the [wiki](https://github.com/intergrav/Adrenaline/wiki). It has a few other helpful resources that I suggest you read, such as troubleshooting info and more. This wiki is often updated with new information.

# 🍉 Sponsor

Need a fast, reliable Minecraft server? Feel free to use my code `devin` for 25% off your first month of any server from Bisect Hosting, supporting me in the process. Click this banner for more information. You can also setup my client/server performance pack [Adrenaline](https://modrinth.com/modpack/adrenaline) to improve your server's optimization while still allowing vanilla clients to join.

[![Bisect Hosting Image](https://www.bisecthosting.com/partners/custom-banners/444cf491-d49c-4b9a-8b2d-250593122b7e.webp)](https://www.bisecthosting.com/devin)
