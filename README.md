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
* Conclusion & Learnings


## Introduction to QPSK 
  Quadrature Phase Shift Keying (QPSK) is a digital modulation technique used to transmit data efficiently in communication systems. It is an improved form of Binary Phase Shift Keying (BPSK) because instead of sending one bit per symbol, QPSK sends two bits at a time by using four different phase shifts of a carrier signal. This allows faster data transmission without increasing the required bandwidth. In QPSK, the incoming digital data is divided into two streams called the in-phase (I) and quadrature (Q) components, which are then modulated separately and combined to form the final signal. Full demodulation of a QPSK signal is the process of recovering the original data at the receiver by separating these components and decoding the transmitted bits. Because of its high spectral efficiency and reliable performance, QPSK is widely used in wireless communication, satellite systems, and modern digital networks.

  In this experiment you'll use the Emona Telecoms-Trainer 101 to convert a model of a digital data signal from serial to parallel and verify its conversion back to serial. Then you'll use the digital data signal as the message for the implementation of the mathematical model of QPSK. Next, you'll implement a model of a typical channel. Then you'll implement the mathematical model of full QPSK demodulation and use it to recover the original digital data signal. Finally, you'll observe the effects of channel noise on the recovered digital data signal.


## Part A: Verifying Serial to Parallel Operation
The Sequence Generator module is used to model digital data. The 2-bit Serial-to-Parallel Converter module is used to split the digital data up into streams of even and odd bits. This function would be the first step in generating a QPSK signal. 

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/Diagrams/fig1.jpeg" alt="A">

The outputs from the Serial-to-Parallel Converter module are connected to the inputs of the 2-bit Parallel-to-Serial Converter module. This function would be the last step in recovering the message from a QPSK signal.
Although the digital signal on the Sequence Generator module’s output is repetitive, the pulse sequence is too irregular for the scope to use the signal to obtain a stable display. So, the scope’s External Trigger Source is connected to the Sequence Generator’s SYNC output for this purpose. The SYNC output is a signal with a single mark that corresponds with the first bit in the Sequence Generator module’s data outputs.

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/622533e635131f223ac106d4d41b99d254238210/Diagrams/fig2.jpeg" alt="A">


<b><i>A.1 - Experiment Result of Part A</i></b> 
<details>
  <summary><b><i>OUTPUT DOCUMENTATION</i></b></summary>

   #### <i>Verifying Serial-to-Parallel Operation Signal</i>
   
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


<b><i>B.1 - Experiment Result of Part B</i></b> 
<details>
  <summary><i>OUTPUT DOCUMENTATION</i></summary>
  
  #### <b><i> STEP BY STEP GENERATING OF THE QPSK </b></i> 
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/9.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/11.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/13.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/15.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/17.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/19.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/20.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/21.jpg" alt="A">

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/22.jpg" alt="A">

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/23.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/24.jpg" alt="A">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/73ea7ea346c758593ef3585d7aac61e79d82fdbf/OUTPUTS/25.jpg" alt="A">

   </details>
   
    
  ## Part C: Modeling Channel Conditions
  The channel in any communications system exhibits the following attributes. First, it’s a source of noise. Second, it is band-limited. Third, it effectively phase shifts the transmission signal because it takes time for the transmitted signal to reach the destination. All three of these attributes can be modelled on the Emona Telecoms-Trainer 101 and this part of the experiment gets you to do so for your QPSK modulation-demodulation system.
   
   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/c39baca04559ed306b9d12fdf2c7c22e37a12931/Diagrams/fig15.jpeg" alt="A">

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/c39baca04559ed306b9d12fdf2c7c22e37a12931/Diagrams/fig16.jpeg" alt="A">

 
 ## Part D: Full Demodulation of the QPSK Signal
 It’s not possible to implement both a QPSK modulator and full demodulator with one Emona Telecoms-Trainer 101. However, it is possible to do with the use of the ETT-101-20 QPSK DEMOD board. Although this is not especially difficult, any errors in wiring can be tricky to locate. So, Part D gets you to set-up the full QPSK demodulator in stages.
 
 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/04af2008164fd8751dc554e7f12396f96b29955d/Diagrams/fig17.jpeg" alt="A">

 The additions to the set-up in Figure above can be represented by the block diagram in Figure below. If you compare it to previous Figure in the preliminary discussion, you’ll notice that it implements the front end of the QPSK demodulator. Ordinarily, the carriers would be generated locally (ie at the receiver) but they have been "stolen" from the modulator so that the pairs of carriers are synchronised which is a necessary requirement for QPSK demodulation.
 
<i>[Note: Methods for synchronising transmitter and local carriers are dealt with in other experiments.]</i>

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/d71025bd78bb31ab625402af1a8a490b0adc3c65/Diagrams/fig23.jpeg" alt="A">

   As the set-up has not yet been "tuned", the signal on the Tuneable LPF module's output likely consists of two quadrature components. Ordinarily, the phase of the local carriers is varied (while maintaining their $90^\circ$ phase separation) to correct for the phase delay in the channel until only one opposing quadrature component appears on each LPF output. As the local carriers (and the bit-clock) have been stolen from the QPSK modulator in this case, this adjustment is modelled by varying the phase delay in the channel instead.

   <b><i>D.1 - Experiment Result of Part D</i></b> 
      <details>
        <summary><i>OUTPUT DOCUMENTATION</i></summary>

   #### <b><i> Full Demodulation of the QPSK Signal </b></i> 

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/d71025bd78bb31ab625402af1a8a490b0adc3c65/OUTPUTS/27.jpg" alt="A">

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/d71025bd78bb31ab625402af1a8a490b0adc3c65/OUTPUTS/29.jpg" alt="A">  

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/d71025bd78bb31ab625402af1a8a490b0adc3c65/OUTPUTS/30.jpg" alt="A">

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/d71025bd78bb31ab625402af1a8a490b0adc3c65/OUTPUTS/31.jpg" alt="A">  

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/92e2e2ae9cad5d9e1600f6206d35fc778fad575a/OUTPUTS/32.jpg" alt="A">

   <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/92e2e2ae9cad5d9e1600f6206d35fc778fad575a/OUTPUTS/34.jpg" alt="A">  

</details>

   ## Part E: Observation of Noise on Recovered Signals
   The current set-up introduces an amount of noise that is 20dB below the maximum that the Noise Generator generates. Part E gets you to observe the effects of noise in the channel on the recovered digital data signal.

   <b><i>D.1 - Experiment Result of Part D</i></b> 
   <details>
     <summary><i>OUTPUT DOCUMENTATION</i></summary>
     

#### <i> Noise on recovered Signals</i>
<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/7215b83cf63e8b4d09f4ccea784e049f4a1648a3/OUTPUTS/38.jpg" alt="A">

     
### Click to watch the Clips!
#### <i>-20dB applied Noise</i>
[![Watch the Video](https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/7215b83cf63e8b4d09f4ccea784e049f4a1648a3/output2/20db.png)](https://drive.google.com/file/d/1GjcUQ4Ub_qOw0YzC5Ka0QSrM8BIKmX96/view?usp=sharing)

#### <i>-6dB applied Noise</i>
[![Watch the Video](https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/7215b83cf63e8b4d09f4ccea784e049f4a1648a3/output2/6db.png)](https://drive.google.com/file/d/13_sHNrLaFC7gMufohNN55UZI_PQN6UWi/view?usp=sharing)

#### <i>-0dB applied Noise</i>
[![Watch the Video](https://github.com/Johnvy-M/COMMS-2-LAB.-Full-Demodulation-of-a-QPSK-signal-/blob/7215b83cf63e8b4d09f4ccea784e049f4a1648a3/output2/0db.png)](https://drive.google.com/file/d/1xZA787ruFhSfD68xDWclEKZ6Lr_SrR_U/view?usp=sharing)

</details>



## Results & Data Gatherings

[<i>Click here to download(Questions & Answers)<i>](https://github.com/Johnvy-M/COMMS-2-LAB.---Modulation-and-Coding-Techniques/blob/d368dc32fd94a497c89736fd5a70b451a786fe89/Data%20%26%20Results/Amplitude_Modulation(exp)%20Tables_and_Data.pdf)

## Conclusion & Learnings
this experiment demonstrated that theoretical modulation schemes rely heavily on precise hardware implementation. By observing the effects of noise and phase shifts, I have gained a better appreciation for the complexities of maintaining signal integrity. The experience in tuning receiver modules has reinforced that rigorous synchronization and meticulous configuration are essential for reliable data recovery in any telecommunications system.

This experiment examined the execution of a QPSK communication system utilizing the Emona Telecoms-Trainer 101. By executing these phases, I connected theoretical knowledge with practical application, enhancing my comprehension of how actual channel impairments—such as noise, bandwidth limitations, and phase shifts—affect signal integrity. An essential takeaway was the significant role of carrier synchronization; employing "stolen" carriers enabled me to focus on the demodulation procedure and practice the manual adjustments needed to obtain separate I and Q bit-streams. In the end, we gained an extra knowledge on how QPSK works. 





















