# pico-Recognizer-ILI9341

Character recognizer based on EMNIST dataset using Raspberry Pi Pico and ILI9341 display.

## Wiring

| Raspberry Pi Pico | ILI9341 Display |
|-------------------|------------------|
| GP2 (MOSI)       | MOSI             |
| GP3 (MISO)       | MISO             |
| GP4 (SCK)        | SCK              |
| GP5 (CS)         | CS               |
| GP6 (DC)         | DC               |
| GP7 (RST)        | RST              |

## Features

## Requirements

## Hardware

## Software

## Installation

## Building

Execute the following commands in your terminal:

```
$ git clone https://github.com/ypsitau/pico-Recognizer-ILI9341.git
$ cd pico-Recognizer-ILI9341
$ git submodule update --init --recursive
```

Open Visual Studio Code in the project folder by executing `code .` in your terminal.
Then press `F7` to build the project and get the binary file `pico-Recognizer-ILI9341.uf2` in the `build` folder.
