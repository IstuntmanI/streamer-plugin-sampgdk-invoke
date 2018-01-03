# samp-streamer-plugin-sampgdk-invoke
The code necessary to invoke [Incognito's Streamer Plugin](https://github.com/samp-incognito/samp-streamer-plugin) functions/callbacks from within a plugin that uses [Zeex's sampGDK](https://github.com/Zeex/sampgdk).

Requirements
------------
- [Incognito's Streamer Plugin v2.9.2 or later](https://github.com/samp-incognito/samp-streamer-plugin). (using an older plugin will throw "`Function not discovered`" errors in the server console when using newer plugin functions, everything else will work fine).
- [Zeex's sampGDK Amalgamation](https://github.com/Zeex/sampgdk).
- Preferably a compiler compatible with the C++14 standard.

Details
-------
* This repository can help GTA:SA-MP users who want to start using sampGDK while also being able to use the Streamer Plugin as a separate plugin, mainly to be able to update it easier for future versions.

Usage
-----
* `streamer.hpp` looks mostly like `streamer.inc`, so it is pretty easy to use Streamer's functions with the definitions that are also available in the Pawn include.

* Functions declarations are available in `streamer.hpp`. Each function type has its own namespace. For example, if in Pawn you did `CreateDynamicObject( ... );` now you can do it like `Plugins::Streamer::Object::Create`, it is still returning the object ID.

* To integrate it in your gamemode you may need to do small changes, such as changing sampGDK's include path or just renaming the `streamer` files.

Additional Notes
----------------
* It may not work fine with an older Visual Studio compiler, I recommend Microsoft Visual Studio 2015/2017 with the latest updates.

* It misses the extended item creation functions (excepting the alternative for `CreateDynamicMapIconEx` [`Plugins::Streamer::MapIcon::CreateEx`] because I needed it once so I created it). I find these extended functions to be too big and I didn't need them, but I may add them if asked to in the future). Also, it may miss some default `streamer.inc` definitions.

* If you want anything missing to be added you can create an issue or send a pull request.
