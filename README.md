# ECE 5760: Playing Card Recognition

## Introduction
For our final project for ECE 5760, we drew inspiration from **[this project](https://hackaday.io/project/27639-rainman-20-blackjack-robot)**, and built a system that recognizes alphanumeric characters on playing cards -- but without the use of OpenCV. The project was intended to be the first step towards implementing an automated blackjack player on a DE1-SoC board. We picked this project because we wanted to combine the unique abilities of the DE1-SoC board, and implement a project that involved computer vision, parallelization, and user interaction.

Our project implementation was distributed over both the FPGA and the HPS, which communicated with each other using parallel I/O ports instantiated in Qsys. We implemented the project in stages, starting with a MATLAB implementation, and then porting the logic over to C, and finally implementing certain parts in Verilog. This helped in testing, debugging, and benchmarking our implementation.

## Overview
Our project uses the FPGA and the HPS on the DE1-SoC board to implement a character recognition algorithm for playing cards. Apart from the board, our hardware consisted of an NTSC bullet camera facing downwards onto a black background, and a wooden platform onto which the camera was mounted. The cards we used were larger print playing cards, since the camera resolution was low, and we needed larger characters to implement accurate character recognition.

The video stream from the camera was input into the FPGA and then stored in memory in the form of image captures. This memory was accessed by the VGA subsystem for display on a VGA screen, and also by the FPGA and the HPS for analysis of the image captured. The FPGA performs contour traversal on the image to find the outline of the card, and detects its corners. This data is sent over to the HPS along with the image itself. The HPS uses this data to rotate the image, extract the symbol on the top left corner, and perform symbol recognition on it. The user interface was implemented on the console using the HPS.

## Implementation
### FPGA
### Qsys Setup
### HPS

## Testing

## Results

## References
**[[1] Blackjack robot on RaspberryPi using OpenCV.](https://hackaday.io/project/27639-rainman-20-blackjack-robot)**

**[[2] Converting Video to SDRAM 640x480 8-bit color.](https://people.ece.cornell.edu/land/courses/ece5760/DE1_SOC/HPS_peripherials/univ_pgm_computer.index.html)**

**[[3] Radial sweep contour following algorithm.](http://www.mdpi.com/1424-8220/16/3/353/htm)**

## Appendices

### Appendix A: Permissions
This group approves this report for inclusion on the course website.

This group approves the video for inclusion on the course YouTube channel.

### Appendix B: Source Code
Access the code here.

### Appendix C: Work Distribution
All group members contributed to all parts of the project, including Verilog logic, HPS code, debugging, and the final report. Dan performed the initial implementation in MATLAB, and helped implement the HPS and Verilog versions. Albert worked on the implementation in C and the user interface. Vaidehi helped port the implementation over from C to Verilog, and debug the HPS and Verilog versions.
