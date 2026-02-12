# X86 Boot Sector Paddle Ball

A minimalist **Paddle ball game written in 16-bit x86 assembly**, designed to run **directly from the boot sector** using only BIOS interrupts.  
No OS, no libs — just pure real-mode assembly.

---



<p align="center">
  <img src="https://img.shields.io/badge/assembly-x86-blue" alt="X86 ASM">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="MIT License">
</p>



![Paddle Ball](paddle_ball.png)


## Features

- Runs as a **bootable program** (`ORG 0x7C00`, boot signature `0xAA55`)
- Uses **BIOS video and keyboard interrupts**
- Text-mode graphics (80×25)
- Player-controlled paddle
- Ball physics with wall & paddle collision
- Score counter with decimal conversion
- Game Over screen with final score
- Fully self-contained in **512 bytes**

---

## Controls

| Key | Action |
|----|-------|
| ← (Left Arrow) | Move paddle left |
| → (Right Arrow) | Move paddle right |
| `Q` | Quit game |

---

## Requirements

- **NASM** (Netwide Assembler)
- An x86 emulator (QEMU recommended) or real hardware
  

---

## Building and Running

Assemble the boot sector using NASM:

```bash
nasm -f bin paddle_ball.asm -o paddle_ball.bin

qemu-system-i386 paddle_ball.bin