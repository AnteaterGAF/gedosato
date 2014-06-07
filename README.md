GeDoSaTo Developer Readme
=========================

General
=======

This file is intended for developers who want to improve GeDoSaTo or use it as a base for other modifications.

All the source code is released under the conditions of the GPLv3, except for
- SuperFastHash
- SMAA
which have their own licensing terms included.

Requirements & Dependencies
===========================

- Visual C++
- The DirectX SDK
- Boost (http://www.boost.org/)
- MinHook (this fork: https://github.com/RaMMicHaeL/minhook)

Contributing
============

The best way to contribute is to send a Github pull request.
If you want to add a major new feature (e.g. DX11 support), I'd appreciate it if you were to contact me before,
so that we can discuss the design a bit.

File Overview
=============

General
-------

- The "pack" folder contains the files for distribution, including end-user documentation, .inis, effects and folders
- "main.*" includes the main function and a few utilities
- The "plugins" folder contain game-specific plugin headers and sources (plugin mappings are defined in "plugins.def")

Wrapping
--------

- The "d3d9*" files implement d3d wrapping
- "detouring.*" files implement function overriding using the Detours library

Utilities
---------

- "settings.*" files implement reading settings (defined in settings.def) from .ini files and querying them
- "key_actions.*" files implement keybindings, together with the Xmacro files "keys.def" and "actions.def"
- "window_manager.*" files implement window management (e.g. borderless fullscreen)
- "d3dutil", string_utils" and "utils" contain various utility functions
- "blacklist.*" manage blacklisting (and whitelisting)

Rendering
---------

- "RenderstateManager.*" is where most of the magic happens, implements detection and rerouting of the games' rendering pipeline state
- "SMAA.*", "VSSAO.*" and "GAUSS.*" are effects optionally used during rendering (derive from the base Effect)
- "Textures.def" is a database of known texture hashes
- "Shaders.def" is a database of known shader hashes
