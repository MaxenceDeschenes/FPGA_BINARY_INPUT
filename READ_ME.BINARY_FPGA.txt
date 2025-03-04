FPGA Digital Input to Binary Display System

Overview
This project is designed for the Altera Cyclone 4 E family FPGA. It implements a digital input system that increments a counter upon pressing a key and displays the result on a 6-digit 7-segment display. The project uses Verilog to implement the logic and control for the FPGA, providing both functionality and efficient resource management.

How It Works
The system utilizes two input keys (key1 and key2) and a 6-digit 7-segment display to show a counter value. The counter increments each time key1 is pressed, and the counting process is disabled when key2 is pressed.

Modules and Components:
7-Segment Display Encoding: Each digit from 0 to 9 is encoded as a 7-bit pattern (active-low), used to control the 7-segment display for each of the 6 digits.

Counting Logic: 
The key1 input triggers the increment of the counter. The value is stored and displayed in a 6-digit format, with the least significant digit (rightmost) displaying the ones place, and the remaining digits displaying higher place values.

Multiplexing:
The display system uses multiplexing to update the 6-digit display. The display data is refreshed at a controlled rate using a counter, ensuring smooth transitions between digits.

Key Debouncing:
The system waits for the keys to be released before taking action again, preventing multiple counts for a single press.

Key Components:
clk: Input clock signal.
key1: Increment counter on press.
key2: Disable counting.
display_out: 7-segment display output for the active digit.
AN: Anode control signals to select which digit to display.
Display Encoding:
The 7-segment display encodes digits from 0-9 as follows:
0: 7'b1000000
1: 7'b1111001
2: 7'b0100100
3: 7'b0110000
4: 7'b0011001
5: 7'b0010010
6: 7'b0000010
7: 7'b1111000
8: 7'b0000000
9: 7'b0010000

Pin Planner: 
Please refer to the Screen Shots for Pin placement and initialization.

System Behavior:
When key1 is pressed, the counter increments by 1.
The current counter value is displayed on the 6-digit 7-segment display.
The system uses multiplexing to cycle through each of the 6 digits.
key2 disables counting when pressed.

Requirements:
FPGA Board: Altera Cyclone 4 E family.
Development Tools: Quartus, ModelSim (for simulation).

Installation:
Load the Verilog code into your FPGA development environment (e.g., Quartus).
Compile and upload the design to the Altera Cyclone 4 E FPGA.
Connect the 6-digit 7-segment display to the appropriate FPGA pins.
Connect key1 and key2 to the FPGA's input pins.
Run the FPGA and observe the output on the display.
