![header](https://github.com/lyangmdrs/extracting_SVC_number_exercise/blob/develop/Img/header.png)
***
# Peripheral Interrupt 

The goal of this exercise is to call a SVC exception and retrieve the SVC number in the handler.

## Supevisor Call (SVC) Instructions 

In a real time sistem, one way to access privileged kernel resources from a user task is using SVC instructions.

When a SVC instructions is called, a number is passed by to the SVC Handler function. From this number, the request can by identified on kernel side.

When the context switch occours, the processor saves the Program Counter (PC) and some others values in memory Stack Frame.

|Memory Stack           |Position from MSP   |
|-----------------------|-------------------|
|`Used Stack Space`     |9|
|`Last Stacked Item`    |8|
|`xPSR`                 |7|
|`Return Addres (PC)`   |6 ☑️|
|`LR`                   |5|
|`R12`                  |4|
|`R3`                   |3|
|`R2`                   |2|
|`R1`                   |1|
|`R0`⬅️*MSP*            |0|
 

At this point, the **MSP** will be pointing to **R0**. So, it is possible to get the **PC** value from the **MSP** just looking 6 memory positions after the **R0**.

> Exercise from [**Embedded Systems Programming on ARM Cortex-M3/M4 Processor**](https://www.udemy.com/course/embedded-system-programming-on-arm-cortex-m3m4/)

***
