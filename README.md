 CE5
===========

##Part one
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
I calculated the hexidecimal values for the above lines of code
```
0x2010002C

0x2011FFDB

0x02119020

0xAC120054
```

The resulting waveform is as follows
![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/waveformone.png)

##Part three
First, I filled in the tables in accordance with what the ORI command does as seen bellow.
![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/table.PNG)


This resulted in the following waveform
![alt tag] (https://raw.githubusercontent.com/TylerSpence/ECE281_CE5/master/waveformpartthree.png)
