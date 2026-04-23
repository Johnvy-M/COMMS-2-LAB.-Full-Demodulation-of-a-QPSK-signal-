<h1 align="center"> <i>COMMS-2-LAB.</i> 
   Full Demodulation of a QPSK signal </h1>

## **Overview**
This is a laboratory report on Communication 2. In this report, viewers can see the input, process, and the output of each experiments. The theoretical explanation behind it will also be discussed and how to use each discipline pratically.    

## Table of Contents
* Introduction to QPSK
* Part A: Verifying Serial to Parallel Operation
* Part B: Generating the QPSK Signal
* Part C: Modeling Channel Conditions
* Part D: Full Demodulation of the QPSK Signal
* Part E: Observation of Noise on Recovered Signals
* Results & Data Gatherings


## Introduction to QPSK 
  Quadrature Phase Shift Keying (QPSK) is a digital modulation technique used to transmit data efficiently in communication systems. It is an improved form of Binary Phase Shift Keying (BPSK) because instead of sending one bit per symbol, QPSK sends two bits at a time by using four different phase shifts of a carrier signal. This allows faster data transmission without increasing the required bandwidth. In QPSK, the incoming digital data is divided into two streams called the in-phase (I) and quadrature (Q) components, which are then modulated separately and combined to form the final signal. Full demodulation of a QPSK signal is the process of recovering the original data at the receiver by separating these components and decoding the transmitted bits. Because of its high spectral efficiency and reliable performance, QPSK is widely used in wireless communication, satellite systems, and modern digital networks.

  In this experiment you'll use the Emona Telecoms-Trainer 101 to convert a model of a digital data signal from serial to parallel and verify its conversion back to serial. Then you'll use the digital data signal as the message for the implementation of the mathematical model of QPSK. Next, you'll implement a model of a typical channel. Then you'll implement the mathematical model of full QPSK demodulation and use it to recover the original digital data signal. Finally, you'll observe the effects of channel noise on the recovered digital data signal.


## Part A: Verifying Serial to Parallel Operation
The Sequence Generator module is used to model digital data. The 2-bit Serial-to-Parallel Converter module is used to split the digital data up into streams of even and odd bits. This function would be the first step in generating a QPSK signal. 

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/Diagrams/fig1.jpeg" alt="A">

The outputs from the Serial-to-Parallel Converter module are connected to the inputs of the 2-bit Parallel-to-Serial Converter module. This function would be the last step in recovering the message from a QPSK signal.
Although the digital signal on the Sequence Generator module’s output is repetitive, the pulse sequence is too irregular for the scope to use the signal to obtain a stable display. So, the scope’s External Trigger Source is connected to the Sequence Generator’s SYNC output for this purpose. The SYNC output is a signal with a single mark that corresponds with the first bit in the Sequence Generator module’s data outputs.

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/Diagrams/fig2.jpeg" alt="A">

<details>
  <summary><b><i>OUTPUT DOCUMENTATION</i></b></summary>

   #### <b><i>Verifying Serial-to-Parallel Operation Signal</i></b>
   
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/OUTPUTS/1.jpeg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/OUTPUTS/2.jpeg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/OUTPUTS/4.jpeg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/OUTPUTS/6.jpeg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/OUTPUTS/7.jpeg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/OUTPUTS/8.jpeg" alt="A">

 </details>

## Part B: Generating the QPSK Signal
setting up a QPSK modulator on its own 
 
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/7ad6adc03c4d909bf52bb017c0bd13096385f6c9/Diagrams/fig11.jpeg" alt="A">

This set-up (excluding the digital data modelling) can be represented by the block diagram in Figure below. Notice that the bit-splitter's two outputs are connected to independent Multiplier modules. The other input to the Multiplier modules are two 100kHz sinewaves that are out of phase with each other by exactly 90°. This is a fundamental requirement of QPSK.

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/7ad6adc03c4d909bf52bb017c0bd13096385f6c9/Diagrams/fig12.jpeg" alt="A">

  To obtain a stable trace on the scope's display, the Trigger Source signal is taken from the Sequence Generator module's SYNC output for the same reason as earlier but this time via a divide-by-2 circuit. The divider is necessary because the digital signals used to phase modulate the two carriers is a frequency that is half the bit rate of the original digital data signal.

<details>
  <summary><b><i>OUTPUT DOCUMENTATION</i></b></summary>
   
  <img src="" alt="A">


  <img src="" alt="A">

  <img src="" alt="A">

  <img src="" alt="A">
















