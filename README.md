# Pendulum NEAT

Pendulum NEAT is a small proof of concept showing how a cart and double
pendulum system can be controlled with a neural network evolved using the
**NEAT** (NeuroEvolution of Augmenting Topologies) algorithm.  The project uses
a simple physics engine and [SFML](https://www.sfml-dev.org/) for real time
rendering of the simulation.  A population of neural networks is trained to
apply horizontal forces on a cart in order to swing up the pendulum and keep it
balanced despite external disturbances.

While still experimental, the code base can be compiled and run on desktop
platforms.

## Build prerequisites

- **CMake** 3.10 or later
- A C++17 compliant compiler (such as `g++` or `clang`)
- **SFML** 2.5 development libraries

On Debian/Ubuntu based systems the dependencies can be installed with:

```bash
sudo apt-get install build-essential cmake libsfml-dev
```

## Building

From the repository root, create a build directory and run CMake:

```bash
cmake -S . -B build
cmake --build build
```

This will produce the executable `Pendulum` in the `build` directory and copy
the `res` folder next to it.

## Running

Run the simulation from the build directory:

```bash
./build/Pendulum
```

The application opens an SFML window showing the training process.  Various
keyboard shortcuts are available (such as `A` to toggle the AI, `D` to start a
demo run, etc.).  Running the program in a headless environment will fail
because it requires an X11/GL context.
