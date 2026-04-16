# NSIGHT_GRAPHICS.md – Software-Specific SOP

## About Nsight Graphics

NVIDIA Nsight Graphics is a graphics debugging and profiling suite for Direct3D,
Vulkan, OpenGL, and related GPU workflows. Depending on the installed version,
it exposes either:

- a **legacy unified CLI** through `ngfx.exe` with activity selection
- a newer **split tool** layout including `ngfx-capture` and `ngfx-replay`

This harness targets the official command-line interfaces rather than the GUI.

## V1 Coverage

### Supported

- installation detection and capability probing
- listing detected installed versions
- detached app launch
- attach to a running PID with an activity
- Frame Debugger capture orchestration
- GPU Trace capture orchestration
- Generate C++ Capture orchestration
- artifact discovery in output directories

### Explicitly Deferred

- replay-helper public commands
- pipeline/resource/shader inspection APIs
- deep analysis comparable to RenderDoc's Python bindings

## Compatibility Notes

- On older Windows installs, `ngfx.exe --help-all` is the primary source of
  truth for supported activities and activity options.
- On newer installs, `ngfx-capture` / `ngfx-replay` may exist alongside `ngfx`.
- This harness prefers capability detection over hard-coded version branching.
- `--nsight-path` can explicitly select one installation when multiple versions coexist.
