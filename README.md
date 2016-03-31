# Up-Down-Counter-EASy68K-in-Assembly


## Introduction

The intent of this work is to implement a counter using EASy68K Assem- bler/Simulator and its Hardware I/O. The counter is working in four different modes that change deppending on the value of two switches. These switches will change the counting pattern keeping the time delay between each interval (1 second).

## Project Description

The project starts in the START section. Here the system is initialized. Counted values are set to 0 and we get the hardware simulator addresses that are going to be necessary throughout the code. These addresses are from display and buttons.
On the next stage loop is called and it will be looping all the time to perform the counting and to check if inputs change. At the begining it checks which switches are on and which switches are off in order to make the decision about working mode. After it gets this information it will jump to the selected mode count modexx and there will check if the counted value reached the maximum. If yes it will call one of the reset functions and it will clear the value; if not a number will be added or subtracted to the last value counted. This number is the number of steps, so it’s just one or two.
After the subtraction or adition operation it will use one register’s most signif- icant word to hold the counting, in this case it will be d7.
Next step is to display data on a segmented display and that’s when print is called. First, all the unnecessary segments are turned off and then the last two digits are used. The data that we have is in hexadecimal format so before it’s displayed it need to be converted to decimal format. That job is performed by Hex2BCD. After the conversion, the code will pick the desired number from the data table digits and will print it using segment7. The delay of one sec- ond is performed using an implemented delay function called DELAY and it’s accessed inside count modexx.
