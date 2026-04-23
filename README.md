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
