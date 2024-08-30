# Generator_Sync
Synchronization Control System for Synchronous Generators
This project demonstrates a an automatic synchronization control system for generators in micogrid that will maintain equal line voltage, frequency (and phase).

## Synchronization parameters
- Line voltage
- Frequency
- Phase angle

## Generator Model
The generator is modeled by using 3 phase synchronous machine. The machine can be used either in the form of generator or motor based on its configuration. The dynamic model of the three-phase synchronous machine is well established and is standardized in the "IEEE Standard 1110-2002". he modelling of electrical machines is based in the direct and quadrature axis for simplicity reasons. The transformation is reducing the three AC quantities into two DC quantities, and is in this way reducing the amount of effort in further calculations. Robert H. Park developed this transformation in 1929, and is now the standard approach in the study of electrical machines.

## Voltage controller
The three phase voltage is sampled and rectified by using 3 phase full wave rectifier using power diodes. The DC converted output is compared with a reference voltage. PI controller is deployed along with a controller to control the voltage of the generator. It is an adaptation of the ST1A excitation system of the IEEE® 421 standard.

## Frequency Controller
The rotor speed is related to the frequency of the generated voltage: $F=PN/120$, where f= frequency of the line voltage, P = Number of poles of the generator, N = rotor speed in rpm. PID controller is used to control the rotor speed to maintain the value of frequency.

## Phase Controller
A phase comparator is used to derive the phase of the line voltages, which uses the Matlab Fourier Block to get phase of each signal. Here only the phase of the fundamental 
frequency waveform is considered.
