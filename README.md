# ECE 5760: Playing Card Recognition

## Introduction
For our final project for ECE 5760, we drew inspiration from **[this project](https://hackaday.io/project/27639-rainman-20-blackjack-robot)**, and built a system that recognizes alphanumeric characters on playing cards -- but without the use of OpenCV. The project was intended to be the first step towards implementing an automated blackjack player on a DE1-SoC board. We picked this project because we wanted to combine the unique abilities of the DE1-SoC board, and implement a project that involved computer vision, parallelization, and user interaction.

Our project implementation was distributed over both the FPGA and the HPS, which communicated with each other using parallel I/O ports instantiated in Qsys. We implemented the project in stages, starting with a MATLAB implementation, and then porting the logic over to C, and finally implementing certain parts in Verilog. This helped in testing, debugging, and benchmarking our implementation.

## Overview
Our project uses the FPGA and the HPS on the DE1-SoC board to implement a character recognition algorithm for playing cards. Apart from the board, our hardware consisted of an NTSC bullet camera facing downwards onto a black background, and a wooden platform onto which the camera was mounted. The cards we used were larger print playing cards, since the camera resolution was low, and we needed larger characters to implement accurate character recognition.

The video stream from the camera was input into the FPGA and then stored in memory in the form of image captures. This memory was accessed by the VGA subsystem for display on a VGA screen, and also by the FPGA and the HPS for analysis of the image captured. The FPGA performs contour traversal on the image to find the outline of the card, and detects its corners. This data is sent over to the HPS along with the image itself. The HPS uses this data to rotate the image, extract the symbol on the top left corner, and perform symbol recognition on it. The user interface was implemented on the console using the HPS.

## Implementation

## Testing

## Results

## References

## Appendices

### Appendix A: Permissions
### Appendix B: Source Code
### Appendix C: Work Distribution

## Custom Builds

You can hire Start Bootstrap to create a custom build of any template, or create something from scratch using Bootstrap. For more information, visit the **[custom design services page](https://startbootstrap.com/bootstrap-design-services/)**.

## About

Start Bootstrap is an open source library of free Bootstrap templates and themes. All of the free templates and themes on Start Bootstrap are released under the MIT license, which means you can use them for any purpose, even for commercial projects.

* https://startbootstrap.com
* https://twitter.com/SBootstrap

Start Bootstrap was created by and is maintained by **[David Miller](http://davidmiller.io/)**, Owner of [Blackrock Digital](http://blackrockdigital.io/).

* http://davidmiller.io
* https://twitter.com/davidmillerskt
* https://github.com/davidtmiller

Start Bootstrap is based on the [Bootstrap](http://getbootstrap.com/) framework created by [Mark Otto](https://twitter.com/mdo) and [Jacob Thorton](https://twitter.com/fat).

## Copyright and License

Copyright 2013-2018 Blackrock Digital LLC. Code released under the [MIT](https://github.com/BlackrockDigital/startbootstrap-scrolling-nav/blob/gh-pages/LICENSE) license.
