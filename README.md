# Effekt8: Chip-8 emulator in Effekt

Aim is to emulate the Chip-8, an interpreted programming language from the 1970s, using the Effekt programming language. The emulator will interpret and execute Chip-8 programs, allowing users to run classic Chip-8 games and applications. This project will leverage Effekt's unique features, such as its effect system, to handle the various operations required by the emulator, including input/output, graphics rendering, and sound.

## Must-have

- [x] Basic Chip-8 instruction set implementation

- [x] Display rendering using Effekt's graphics capabilities via html canvas
- [x] Keyboard input handling
- [x] Loading and running Chip-8 ROMs

## Can-have

- [x] Graphical user interface for loading and managing ROMs
- [ ] Debugger with step-through execution and breakpoints
- [ ] Save and load state functionality
- [ ] Sound support for Chip-8 audio

## Will-not-have

- Networked multiplayer support
- Support for non-Chip-8 related features or extensions
- Comprehensive test suite for the emulator

## Effects and handlers

I haven't decided on the exact namings of the effects and handlers yet, but here are some ideas for the effects that I am planning to use:

- Input/Output effects for handling keyboard and display
- State effects for managing the emulator's memory and registers
- Exception effects for handling invalid instructions or errors
- Timer effects for implementing Chip-8 timers and delays

## FFI and libraries

I am planning on using JS (js-web backend) to do the GUI related tasks, such as rendering the display and handling keyboard input. I will need to write some glue code to interface with the Chip-8 emulator's internal state and the external JS environment.

## Running The Project

To run the project, you need to have Effekt installed on your machine. You can find instructions on how to install Effekt [here](https://effekt-lang.org/docs)

After installing Effekt, you can run the project by executing the following command in the project's root directory:

```bash
effekt src/main.effekt --backend js-web --includes .
```

This will then produce a `main.html` and `main.js` file in the `out` directory. You can open the `main.html` file in your browser to run the emulator.

Chip-8 ROMs can be found online and loaded into the emulator by clicking the "Load ROM" button in the GUI.

## Resources

- [Cowgod's Chip-8 Technical Reference](http://devernay.free.fr/hacks/chip8/C8TECH10.HTM)
