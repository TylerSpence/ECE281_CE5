 CE5
===========

##Part one
Using the example from the book I created the following commands.
``` 
# $s0 = a 
addi $s0, $0, 44   

# $s1 = b
 addi $s1, $0, -37 

# a + b = c
add $s2, $s0, $s1 

#store c
sw $s2, 0x54($0)    
```

##Part two
I calculated the hexidecimal values for the above lines of code.
```
0x2010002C

0x2011FFDB

0x02119020

0xAC120054
```

The resulting waveform is as follows
![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/waveformone.png)

##Part three
Fist I modified the diagram by adding a zero extend and a second mux within the ALU logic section as seen below. 

![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/diagram.jpg)

Then, I filled in the tables in accordance with what the ORI command does as seen below.

![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/table.PNG)

Then I had to modify the vhd code to apply the changes that I designed.


I then converted the desired command into hex, as seen below.
```
0x36538000
```
This resulted in the following waveform
![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/waveformpartthree.png)


##Documentation
C3C Eric Wardner and JP Terragnoli helped me get the appropriate values on the waveform by navigating through the options.

C3C Wardner and I checked our hex values with each other to ensure accuracy with the waveform.
