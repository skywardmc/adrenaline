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

Adrenaline is a modpack comprised of the **best combination of mods** (e.g. Sodium and Lithium, along with many more) that significantly improves rendering performance, logic performance, memory usage, and more - all without compromising on the game's vanilla looks and features! It is designed to be simple and not include any quality-of-life mods, along with not including redundant performance mods. Because of this simplicity, the modpack is compatible with a very wide range of devices and can be updated to the latest versions very quickly. Want more features? No problem! Adrenaline serves as a great foundation for performance - simply add your favorite mods on top.

# 📥 Installation Guide

**Please be sure to read Sodium's [Driver Compatibility](https://github.com/CaffeineMC/sodium-fabric/wiki/Driver-Compatibility) section on the wiki before installing Adrenaline. It contains some important instructions on preventing crashes and other performance issues.**

If you would like to install the modpack, go to this page on [the Additive website](https://additive.intergrav.xyz/downloads) (install instructions are the same). You can install the modpack with a third party launcher or our standalone installer. After you install, you can figure out how to tweak things to give greater optimizations in the [post-install](https://github.com/intergrav/Adrenaline/wiki/Post-install) section of the wiki. This includes procedures such as increasing your allocated memory and tweaking your game settings for your device.

After installing the modpack, you can easily add your favorite mods so long as they are compatible with the Minecraft version you are playing on. The wiki also has some recommendations on possibly improving performance further with other mods that are not suitable to be included in Adrenaline by default.

# 🎯 Goals

### 🚀 Improve performance

Adrenaline aims to significantly improve rendering and game logic performance, along with memory and hardware usage, without compromising on the game's looks or features in any way. This is done with various optimization mods that are actively tested for stability and improvement. Some mods are also pre-configured. Adrenaline wouldn't exist with projects like [Sodium](https://modrinth.com/mod/sodium), so I advise you to donate to mod authors and contributors if you can.

### 🪶 Stay lightweight

I only pick the combination of mods that work best with eachother, and don't include performance mods that aren't necessary or often break compatibility with other mods or device hardware. I also don't include any quality of life mods in the pack for the sole purpose of keeping it simple and flexible. This simplicity allows you to very easily build your own modpacks based on Adrenaline, or simply install Adrenaline and play with your favorite mods.

### ⚙️ Source-available

All mods in Adrenaline are either open-source or source-available, which means you can view the code of mods and see exactly what they are doing. Adrenaline is also available as [packwiz projects on GitHub](https://github.com/skywardmc/adrenaline) so that you can easily view what's being changed, contribute if you would like to, or fork the modpack to create your own project. If you would like to view the mods shipped with Adrenaline, simply look at the dependencies in the Modrinth page or look in the Git repository.

# ✅ Hardware Compatibility

Adrenaline supports the use of graphics cards with drivers that are compatible with OpenGL 4.6. Most graphics cards released in 2010 or later are compatible. This includes the following hardware:

- Intel HD Graphics 500 Series (Skylake) or newer
- Nvidia GeForce 400 Series (Fermi) or newer
- AMD Radeon HD 7000 Series (GCN 1) or newer

In some cases, older graphics cards may also work (as long as they have drivers which support OpenGL 3.3) but they are not officially supported and may not be compatible in the future.

Android devices that use OpenGL translation layers (such as GL4ES, ANGLE, etc) are not supported and will likely not work with Adrenaline's set of mods. These translation layers do not implement required functionality and suffer from underlying driver bugs which cannot be worked around.

If you are running into problems, you should make sure that your graphics drivers are up-to-date. I also recommend taking a look at [this page](https://github.com/CaffeineMC/sodium-fabric/wiki/Driver-Compatibility) on the Sodium wiki.

*The majority of this was taken from Sodium's hardware compatibility section. I'll update this accordingly if anything is changed.*

# 🐛 How to Report Issues

Experiencing bugs, crashes, or other issues? Feel free to open an issue on the [issue tracker](https://github.com/intergrav/Adrenaline/issues). Be sure to include necessary information like your hardware/software (e.g. GPU and CPU, modpack version and OS) so that it's easier for us to find issues and resolve them.

# ❓ Frequently Asked Questions

For a few frequently asked questions, along with tons of other information, consider visiting the [wiki](https://github.com/intergrav/Adrenaline/wiki). It has a few other helpful resources that I suggest you read, such as troubleshooting info and more. This wiki is often updated with new information.

# 🍉 Sponsor

Need a fast, reliable Minecraft server? Feel free to use my code `devin` for 25% off your first month of any server from Bisect Hosting, supporting me in the process. Click this banner for more information. You can also setup my server-side performance pack called [Adrenaserver](https://modrinth.com/modpack/adrenaserver) to improve your server's optimization while still allowing vanilla clients to join.

[![Bisect Hosting Image](https://www.bisecthosting.com/partners/custom-banners/444cf491-d49c-4b9a-8b2d-250593122b7e.webp)](https://www.bisecthosting.com/devin)

*Adrenaline's description is heavily inspired by [Sodium](https://modrinth.com/mod/sodium)'s description and also includes some information from them. Description last updated: March 25, 2024*