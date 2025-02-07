# Effekt8 - CHIP-8 Emulator Architecture

## Overview

Effekt8 is a CHIP-8 emulator implemented in the Effekt programming language, targeting JavaScript web browsers as the primary platform. The emulator features a futuristic UI, customizable display colors, and full CHIP-8 instruction set support.

## Core Components

### 1. CPU (`src/cpu.effekt`)

- Implements the CHIP-8 virtual machine
- Handles instruction fetching, decoding, and execution
- Manages system timers (delay and sound)
- Key features:
  - 16 8-bit registers (V0-VF)
  - 4KB memory management
  - 16-level stack
  - Program counter and index register
  - Timers running at 60Hz

### 2. Renderer Interface (`src/renderer.effekt`)

- Abstract interface for display output
- Defines common operations:
  - Screen drawing and clearing
  - Input handling
  - Audio control
  - System logging

### 3. Web Renderer (`src/renderers/js.effekt`)

- Implements the renderer interface for web browsers
- Features:
  - 64x32 pixel display using HTML Canvas
  - Customizable foreground/background colors
  - Keyboard input mapping
  - Audio beep implementation
  - System log display
  - Modern, futuristic UI design

## Implementation Details

### Memory Layout

- Total 4KB (4096 bytes) of memory
- First 512 bytes (0x000-0x1FF) reserved for interpreter
- Programs start at memory location 0x200
- Font set stored in interpreter space

### Display

- Resolution: 64x32 pixels
- Monochrome display with customizable colors
- Implements sprite drawing with collision detection
- Supports XOR drawing operation

### Input System

- 16 keys (0-F) mapped to modern keyboard
- Key mapping can be found in the README.md file.

### Timers

- Delay timer: General purpose, counting down at 60Hz
- Sound timer: Generates tone when non-zero, 60Hz

### Technical Features

- Cross-platform web-based implementation
- Efficient instruction execution
- Accurate timing control
- Modern user interface
- Real-time debugging through system logs

## Project Structure

- `src/`: Source code directory
  - `cpu.effekt`: CPU implementation
  - `renderer.effekt`: Renderer interface
  - `renderers/js.effekt`: Web renderer implementation (JavaScript Web)

## Design Decisions

1. **Modular Architecture**

   - Separation of concerns between CPU and display
   - Abstract renderer interface for potential multiple backends
   - Clean separation of system components

2. **Web-First Approach**

   - JavaScript/HTML5 target for wide accessibility
   - Canvas-based display for efficient rendering
   - Modern web technologies for UI and audio

3. **User Experience**

   - Futuristic, clean UI design
   - Customizable display colors
   - Real-time system logging
   - Responsive keyboard controls

4. **Performance Considerations**
   - Efficient memory management
   - Optimized display updates
   - Proper timing implementation
   - Responsive input handling

## Future Improvements

1. **Additional Features**

   - Save states
   - Speed control
   - Debug mode

2. **Potential Enhancements**
   - Additional renderer backends
   - Enhanced audio capabilities
   - Extended debugging tools
   - Configuration persistence

## Dependencies

- Effekt programming language
- Web browser with Canvas and Web Audio support for JS backend
