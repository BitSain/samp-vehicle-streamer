[![sampctl](https://img.shields.io/badge/sampctl-samp--vehicle--streamer-2f2f2f.svg?style=for-the-badge)](https://github.com/BenBurak/samp-vehicle-streamer)

[![GitHub Release](https://img.shields.io/github/release/BenBurak/samp-vehicle-streamer.svg)](https://github.com/BenBurak/samp-vehicle-streamer/releases/latest) [![Download](https://img.shields.io/github/downloads/BenBurak/samp-vehicle-streamer/total?color=blue)](https://github.com/BenBurak/samp-vehicle-streamer/releases/latest) [![License](https://img.shields.io/github/license/BenBurak/samp-vehicle-streamer?color=blue)](https://github.com/BenBurak/samp-vehicle-streamer)

# SA-MP Vehicle Streamer Plugin
This plugin was created for SA-MP (San Andreas Multiplayer). The purpose of the plugin is to exceed vehicle limits. Since it is coded in C++, Pawn payloads are avoided.

This maintenance branch preserves the existing Pawn API and fixes several problems from the original test release, including the tick-rate state, timer overflow, vehicle cleanup during unload, invalid component-slot indexing, duplicate player entries and missing source files in the Visual Studio project.

## Documentation

The public native and callback declarations are available in `vehicle-streamer.inc`. The plugin still requires SA-MP's vehicle pool and should be tested with the target server build before production use.

## Installation

(SAMPCTL neccessary) Simply install to your project:

```bash
sampctl install nexquery/samp-vehicle-streamer
```

## Maintenance notes

The original repository contains issue [#3](https://github.com/nexquery/samp-vehicle-streamer/issues/3), reporting vehicles that do not respawn. The synchronization timer now uses one shared 64-bit state and no longer overflows after the process has been running for a long time. Respawn behavior continues to follow the `respawn_delay` passed to `CreateDynamicVehicle`; a negative delay intentionally disables automatic SA-MP respawn.
