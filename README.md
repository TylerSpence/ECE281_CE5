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

The waveform starts at 200ns because of a delay in the testbench coding. 

The waveform begins by loading 2c (44 in hex) and then db (which when preceeded by the f's is -37) to rd1 and rd2 respectively then adds them together and stores the result in wd, which results in 7 (the correct number) at 220ns. It then stores it at address 054 as seen at 230ns on wd into rd2 (which corresponds to s2). 
##Part three
Fist I modified the diagram by adding a zero extend and a second mux within the ALU logic section as seen below. 

![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/diagram.jpg)

Then, I filled in the tables in accordance with what the ORI command does as seen below.

![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/table.PNG)

Then I had to modify the vhd code to apply the changes that I designed.

This was accomplished by modifying every instance of alusrc to make it two bits wide so that it could control both the existing mux and the new mux. This also meant modifying the functionality codes for the instruction to include a second bit for regdst. 

The only other essential change was adding in the second mux in the ALU logic and declaring a new signal to appropriately use it. 

I then converted the desired command into hex, as seen below.
```
0x36538000
```
This resulted in the following waveform
![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/waveformpartthree.png)

The new command works, as noticeable in the time after 240ns. 8000 is or'ed with 7, resulting in 8007, as predicted. 
##Dificulties
I had issues getting the waveform to work because of not knowing to name it the right thing, I ended up fixing it as described below.

I started out by tring to use a 3 input mux instead of two as can be seen in an earlier commit, but i decided that it was simpler and more elegant to just use two. 
##Documentation
C3C Eric Wardner and JP Terragnoli helped me get the appropriate values on the waveform by navigating through the options.

C3C Wardner and I checked our hex values with each other to ensure accuracy with the waveform.
