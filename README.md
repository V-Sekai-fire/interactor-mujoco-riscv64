# interactor-mujoco-riscv64

The seed of a riscv64 build of MuJoCo to drive as a libriscv sandboxed guest: the vendored source, its CMake recipe and a C wiring layer.

## What it is for

It holds MuJoCo's source at a pinned upstream commit under `thirdparty/`, a CMake recipe that adds it as a library target, a small C layer that initialises, steps and closes a simulation, and a free-fall test against the closed-form answer. The riscv64 cross-build and the guest bindings are not in the repository.

## Build and run

The repository has no top-level build. `cmake/mujoco.cmake` is included from a CMake project at the repository root, which then links the `mujoco` target with `src/physics/`.

## Licence

The repository does not state a licence for its own code. The vendored MuJoCo source carries its own Apache-2.0 licence.
