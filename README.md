# Pac-Man Assembly Game

[![Assembly](https://img.shields.io/badge/Assembly-x86-blue.svg)](https://en.wikipedia.org/wiki/X86_assembly_language)
[![MASM32](https://img.shields.io/badge/MASM32-Compatible-green.svg)](http://www.masm32.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A classic Pac-Man game implementation written in x86 Assembly language using the Irvine32 library. This project demonstrates fundamental game development concepts, character movement, and console-based graphics in Assembly.

## 🎮 Features

- **Console-based Graphics**: ASCII art maze rendered in real-time
- **Player Movement**: Arrow key controls for Pac-Man navigation
- **Collision Detection**: Basic boundary checking to prevent out-of-bounds movement
- **Real-time Rendering**: Smooth character movement with screen clearing and redrawing
- **Modular Design**: Well-structured procedures for easy maintenance and extension

## 🚀 Quick Start

### Prerequisites

- **MASM32 SDK**: Microsoft Macro Assembler 32-bit
- **Irvine32 Library**: Required for console I/O operations
- **Windows OS**: Compatible with Windows 7/8/10/11
- **Visual Studio** (recommended) or **MASM32 Editor**

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/pacman-assembly.git
   cd pacman-assembly
   ```

2. **Ensure Irvine32 library is installed**
   - Download from [Kip Irvine's website](http://kipirvine.com/asm/)
   - Place `Irvine32.inc` and `Irvine32.lib` in your project directory

3. **Assemble and link**
   ```bash
   ml /c /coff pacman.asm
   link /subsystem:console pacman.obj irvine32.lib kernel32.lib
   ```

4. **Run the game**
   ```bash
   pacman.exe
   ```

## 🎯 How to Play

- **Arrow Keys**: Move Pac-Man around the maze
  - ↑ **Up Arrow**: Move up
  - ↓ **Down Arrow**: Move down
  - ← **Left Arrow**: Move left  
  - → **Right Arrow**: Move right
- **Objective**: Navigate Pac-Man (P) through the maze
- **Boundaries**: Pac-Man cannot move through walls (@) or outside the maze

## 🏗️ Architecture

### File Structure
```
pacman-assembly/
├── pacman.asm          # Main game source code
├── README.md           # This file
├── LICENSE             # License information
└── docs/               # Additional documentation
    ├── CONTRIBUTING.md # Contribution guidelines
    └── CHANGELOG.md    # Version history
```

### Code Organization

#### Data Section
- **Map Layout**: 13-row ASCII maze stored as byte arrays
- **Player Position**: `pacRow` and `pacCol` coordinates
- **Wall Characters**: `@` represents maze walls
- **Dots**: `.` represents collectible items (future enhancement)

#### Procedures

| Procedure | Purpose | 
|-----------|---------|
| `main` | Game initialization and main loop | 
| `DrawMap` | Renders maze and player position | 
| `MoveUp` | Handles upward movement | 
| `MoveDown` | Handles downward movement | 
| `MoveLeft` | Handles leftward movement | 
| `MoveRight` | Handles rightward movement | 

### Game Loop Flow

1. **Initialize**: Clear screen and set starting position
2. **Render**: Draw current maze state with player
3. **Input**: Wait for and process keyboard input
4. **Update**: Modify player position based on input
5. **Repeat**: Continue until program termination

## 🔧 Technical Details

### Assembly Directives
- `.486`: Target 486 processor instruction set
- `INCLUDE Irvine32.inc`: Include Irvine library procedures
- `.data`: Data segment for variables
- `.code`: Code segment for procedures

### Memory Management
- **Static Allocation**: Maze stored in data segment
- **Register Usage**: Efficient use of EAX, EBX, ECX, EDX, ESI
- **Stack Management**: Proper procedure calls with RET instructions

### I/O Operations
- **Console Output**: `WriteString`, `WriteChar`, `CrLf`
- **Screen Control**: `Clrscr`, `Gotoxy`
- **Keyboard Input**: `ReadKey` for arrow key detection

## 🚧 Future Enhancements

- [ ] **Dot Collection**: Implement scoring system with collectible dots
- [ ] **Ghost AI**: Add computer-controlled enemies
- [ ] **Power Pellets**: Special items for temporary ghost vulnerability
- [ ] **Level Progression**: Multiple maze layouts
- [ ] **Sound Effects**: Basic beep sounds for actions
- [ ] **High Score**: Persistent score tracking
- [ ] **Color Graphics**: Enhanced visual presentation

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](docs/CONTRIBUTING.md) for details.

### Development Setup
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Coding Standards
- **Comments**: Document all procedures and complex logic
- **Naming**: Use descriptive variable and procedure names
- **Formatting**: Consistent indentation and spacing
- **Testing**: Verify functionality before submitting

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Muhammad Abdullah Nadeem**  - [Muhammad Abdullah](https://github.com/abdullahnadeem10-fast)

## 🙏 Acknowledgments

- **Kip Irvine** - For the excellent Irvine32 assembly library
- **MASM32 Community** - For tools and documentation
- **Original Pac-Man** - Namco's classic arcade game inspiration

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/yourusername/pacman-assembly/issues) page
2. Create a new issue with detailed description
3. Include system information and error messages
4. Tag appropriately (bug, enhancement, question)

## 📊 Project Statistics

- **Lines of Code**: ~1281
- **Assembly Directives**: 4
- **Supported Platforms**: Windows (32-bit/64-bit)

---

*Made with ❤️ and Assembly language*
