# pico-Recognizer-ILI9341

Character recognizer based on EMNIST dataset using Raspberry Pi Pico and ILI9341 display. A demonstration application of machine learning on microcontrollers using [pico-jxglib](https://github.com/ypsitau/pico-jxglib) library.

## Demonstration

[![Demonstration](https://img.youtube.com/vi/p4s3oFeSuCg/0.jpg)](https://youtu.be/p4s3oFeSuCg)

## Requirements

Following components are required to build this project:

- Raspberry Pi Pico or Pico W or Pico 2 or Pico 2 W
- ILI9341 display module
- Breadboard and jumper wires
- Micro USB cable

## Wiring

Connect the Raspberry Pi Pico to the ILI9341 display as follows:

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

GPIO0 and GPIO1 are used to select the TFLite model to recognize characters. Each model is trained on a different subset of the EMNIST dataset. Connect GPIO0 and GPIO1 to either GND or leave them unconnected (NC) to select the desired model as shown below:

|GPIO1|GPIO0|Training Dataset |Recognizable Characters|
|-----|-----|-----------------|-----------------------|
| NC  | NC  | EMNIST Balanced |0-9, A-Z, a, b, d, e, f, g, h, n, q, r, t |
| NC  | GND | EMNIST MNIST    |0-9                    |
| GND | NC  | EMNIST Letters  |A-Z                    |
| GND |GND  | EMNIST ByMerge  |0-9, A-Z, a, b, d, e, f, g, h, n, q, r, t |

## Installation

In order to install the pre-built binary file to your Pico board, follow these steps:

1. Press and hold the BOOTSEL button on your Pico board while connecting it to your computer via USB. Release the BOOTSEL button after connecting.
2. Your Pico board should appear as a removable drive such as `D:`. Copy one of the following UF2 files to the drive:

   |Pico Board|UF2 File|
   |-----------|------------|
   |Pico |[pico-Recognizer-ILI9341.uf2](https://github.com/ypsitau/pico-Recognizer-ILI9341/releases/latest/download/pico-Recognizer-ILI9341.uf2)            |
   |Pico 2 |[pico2-Recognizer-ILI9341.uf2](https://github.com/ypsitau/pico-Recognizer-ILI9341/releases/latest/download/pico2-Recognizer-ILI9341.uf2)  |

## Building

When you want to build the project from source code, follow these steps:

1. Execute the following commands in your terminal:

   ```
   $ git clone https://github.com/ypsitau/pico-Recognizer-ILI9341.git
   $ cd pico-Recognizer-ILI9341
   $ git submodule update --init --recursive
   ```

2. Open Visual Studio Code in the project folder by executing `code .` in your terminal. Then press `F7` to build the project and get the binary file `pico-Recognizer-ILI9341.uf2` in the `build` folder.
