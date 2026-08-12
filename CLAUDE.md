# LazyRiver

## Overview
Standalone Windows desktop executable built in Unreal Engine. The player experiences a lazy-river ride: a red inner tube carried down a river/rapids environment. Motion data captured from the physical inner tube is run through a custom interpreter that compiles it into drive signals for a physical motion rig — the software is effectively the sim/render layer for a motion-simulator attraction, not just a game.

This is a new repo on the same GitHub account as other Vance projects, currently unscaffolded (empty directory as of 2026-08-12).

## Core Components
1. **Unreal Engine project** — river/rapids environment, red inner tube actor, camera/render pipeline. Standalone packaged EXE, desktop only (no VR/console target).
2. **Motion capture ingest** — reads real-time motion data off the physical inner tube (sensor/hardware TBD).
3. **Custom interpreter** — translates raw inner-tube motion data into commands/waveforms that drive the physical motion rig (rig hardware/protocol TBD).
4. **Motion rig output** — the compiled drive signal target; rig make/model and control interface TBD.

## Unreal Engine / MCP Setup
- Target engine: **Unreal Engine 5.8+** (first version to ship the built-in "Unreal MCP" plugin).
- MCP source: **official first-party Unreal MCP plugin**, embedded in the editor process, served locally at `http://127.0.0.1:8000/mcp`.
- This lets Claude Code drive the editor directly — spawn/place actors, edit Blueprints, author materials, script Sequencer and Niagara, set up Control Rig — which is directly useful for building the rapids environment and prototyping the motion-rig interpreter's rig-side test scaffolding.
- Enable the plugin in the UE project (Edit > Plugins > search "Unreal MCP") and confirm the local MCP endpoint is running before expecting Claude to interact with the editor.

## Open Questions / TBD
- Inner tube motion sensor hardware and data protocol (IMU? custom board? serial/BLE/USB?).
- Motion rig hardware, axes of freedom, and control interface/protocol.
- Target Unreal Engine version pin once project is scaffolded.
- Repo name/URL on GitHub (not yet created).

## Conventions
(To be filled in once the UE project is scaffolded — folder structure, naming, Blueprint vs C++ split, etc.)
