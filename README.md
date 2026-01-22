# pico-Recognizer-ILI9341

Character recognizer based on EMNIST dataset using Raspberry Pi Pico and ILI9341 display. A demonstration application of machine learning on microcontrollers using [pico-jxglib](https://github.com/ypsitau/pico-jxglib) library.

## Requirements

- Raspberry Pi Pico or Pico W or Pico 2 or Pico 2 W
- ILI9341 display module
- Breadboard and jumper wires
- Micro USB cable

## Wiring

| Raspberry Pi Pico | ILI9341 Display |
|-------------------|-----------------|
| GPIO2 (SPI0 SCK)  | T_CLK           |
| GPIO3 (SPI0 TX)   | T_DIN           |
| GPIO4 (SPI0 RX)   | T_DOUT          |
| GPIO8             | T_CS            |
| GPIO9             | T_IRQ           |
| GPIO10            | RESET           |
| GPIO11            | DC              |
| GPIO12            | CS              |
| GPIO13            | LED             |
| GPIO14 (SPI1 SCK) | SCK             |
| GPIO15 (SPI1 TX)  | SDI (MOSI)      |

GPIO0 and GPIO1 are used to select the recognition model.

|GPIO1|GPIO0|Training Dataset |Recognizable Characters|
|-----|-----|-----------------|-----------------------|
| NC  | NC  | EMNIST Balanced |0-9, A-Z, a-z          |
| NC  | GND | EMNIST MNIST    |0-9                    |
| GND | NC  | EMNIST Letters  |A-Z                    |
| GND |GND  | EMNIST ByMerge  |0-9, A-Z, a-z          |

## Installation

## Building

1. Execute the following commands in your terminal:

   ```
   $ git clone https://github.com/ypsitau/pico-Recognizer-ILI9341.git
   $ cd pico-Recognizer-ILI9341
   $ git submodule update --init --recursive
   ```

2. Open Visual Studio Code in the project folder by executing `code .` in your terminal. Then press `F7` to build the project and get the binary file `pico-Recognizer-ILI9341.uf2` in the `build` folder.

## Demonstration

[![Demonstration](https://img.youtube.com/vi/oYj4OYiUWKs/0.jpg)](https://youtube.com/shorts/oYj4OYiUWKs)