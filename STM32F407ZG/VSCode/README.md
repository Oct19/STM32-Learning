# STM32F407-Core-Board-Example

## Function

1. Blink two on board LEDs alternatively
2. Can be used as project template

## Hardwares
- Board:STM32F407最小系统板/STM32F407 Core Board
- Connection plan A: PC connect to on board USB_TTL terminal using USB cable (cannot debug with this method)
- Connection plan B: Use ST-Link V2 to connect
- Pin out:
    - PF9: LED_RED
    - PF10: LED_GREEN

## Software setup

1. Install VS Code
    - C/C++ IntelliSense
    - CMake Tools
    - Cortex-Debug
    - Makefile Tools
2. Install STM32CubeMX
3. Install Make
    - Binary
    - Dependency
4. Install Git
5. Install OpenOCD
6. Install GCC ARM Toolchain
7. Add environment variables:
    - Make/bin
    - ARM GCC/bin
    - OpenOCD/bin
8. Install FlyMcu
9. Install XCOM
10. Install CH34x Driver
11. Install ST-Link Driver


## Instructions

1. To modify Pinout and configuration, use STM32CubeMX to open .ioc file. Once new codes are generated, old code will be stored in Inc/Backup and Src/Backup
2. Modify code if needed
3. Press Ctrl+Shift+b to 'Build all'. The script is written in .vscode/tasks.json
4. Use FlyMcu to write to board
    - Locate generated hex file
    - Search for Port
    - Set bps:76800
    - DTR的低电平复位，RTS高电平进BootLoader
    - Check: 编程后执行
    - Check: 编程前重装文件
    - Uncheck: 编程刀FLASH时写选项字节
    - 开始编程(will take time to erase and write)
5. Use XCOM to read signal from board
    - Select port
    - Set baudrate as 115200
    - Open port

## Reference

- STM32F407最小系统板开发指南-HAL库函数版本_V1.2 章节3.4
- YouTube
    - STM32 toolchain for Windows - Part 1 https://youtu.be/jcy5TpbXfAY
    - Configure  VSCode for Embedded project (STM32) with Make https://youtu.be/jcy5TpbXfAY