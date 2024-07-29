UART Verilog Module

Description

This repository contains the Verilog code for a Universal Asynchronous Receiver-Transmitter (UART) module. 

The module facilitates serial communication by transmitting and receiving data bits over a single line.

Module: top

Functionality

The top module handles both transmission (TX) and reception (RX) of serial data.

It operates based on a specified baud rate and clock frequency.

Parameters
  1. clk_value: Clock frequency (default is 100,000 Hz).
  2. baud: Baud rate (default is 9600 bps).
  3. Port Definitions
  4. input clk: System clock.
  5. input start: Start signal for transmission.
  6. input [7:0] txin: Data to be transmitted.
  7. output reg tx: Transmitted serial data.
  8. input rx: Received serial data.
  9. output [7:0] rxout: Data received.
  10. output rxdone: Indicates reception completion.
  11. output txdone: Indicates transmission completion.
    
Implementation

Baud Rate Generation

The baud rate generator produces a trigger signal at intervals defined by the clock frequency and baud rate.

Transmission Logic

Data transmission is managed by shifting out bits from a buffer (txData). 

The transmission state machine handles the idle, sending, and checking states.

Reception Logic

Data reception is managed by capturing bits into a buffer (rxdata). The reception state machine handles idle, waiting, receiving, and checking states.
