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
