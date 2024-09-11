# First and foremost
The notion of the floating point is against the fixed point which means the decimal point is floating, that is to say, when the integer part has fewer numbers, then the decimal part can contain more numbers, thus a bigger range of numbers can be stored in the same capacity.

The standards of IEEE-754 demand the floating-point numbers be stored like this:
![image](https://github.com/user-attachments/assets/e740f262-2377-4f7e-8560-c796e50781bb)
              2⁸  2⁷  2⁶  2⁵  2⁴  2³  2²  2¹ 2­⁻¹2⁻²2⁻³2⁻⁴2⁻⁵2⁻⁶2⁻⁷2⁻⁸2⁻⁹2⁻¹⁰2⁻¹²2⁻¹³2⁻¹⁴2⁻¹⁵2⁻¹⁶2⁻¹⁷2⁻¹⁸2⁻¹⁹2⁻²⁰2⁻²¹2⁻²²2⁻²³2⁻²⁴
# Scientific Notation:
                      sign              exponent
                         +   7.125 x e10
                      1 <= valid numbers <2
So:
1. The sign bit stores the sign:	0	-->	  positive numbers ;  1	 -->     negative numbers
2. The biased exponent stores the exponent.
3. The fraction stores the valid numbers.
# The process of transforming a float number into the binary system:
1. take the **7.125** as an example  
2. the integer part:0000 0111                 
3. the fractional part:             
4. 0.125x2=0.25  take the integer part:0  
5. 0.25x2=0.5.  take the integer part:0  
6. 0.5x2=1.0  take the integer part:1  
7. get the result:    .001  
8. combine it, get: 111.001    
9. move leftward 2 bits, get: 1.11001  
10. so the exponent is 2  
11. then the biased exponent equals: 127+2=129   
(tips: as the biased exponent part has no sign, set the middle number 127 as the zero)   
12. the binary number of 129 is: 1000 0001    
13. so the result is:   
0 | 1000 0001 | 1100 1000 0000 0000 0000 000   
