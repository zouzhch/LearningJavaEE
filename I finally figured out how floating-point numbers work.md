First and foremost, the notion of the floating point is against the fixed point which means the decimal point is floating, that is to say, when the integer part has fewer numbers, then the decimal part can contain more numbers, thus more range of numbers can be stored in a same capacity.



The standards of IEEE-754 demand the floating-point numbers be stored like this:

![](https://cdn.nlark.com/yuque/0/2024/png/47471281/1725442045437-d05f3692-453a-4b21-9f97-d88c7f24a36d.png)

       2<sup>8  </sup>2<sup>7  </sup>2<sup>6  </sup>2<sup>5  </sup>2<sup>4  </sup>2<sup>3  </sup>2<sup>2  </sup>2<sup>1 </sup>2<sup>-1</sup>2<sup>-2</sup>2<sup>-3</sup>2<sup>-4</sup>2<sup>-5</sup>2<sup>-6</sup>2<sup>-7</sup>2<sup>-8</sup>2<sup>-9</sup>2<sup>-10</sup>2<sup>-11</sup>2<sup>-12</sup>2<sup>-13</sup>2<sup>-14</sup>2<sup>-15</sup>2<sup>-16</sup>2<sup>-17</sup>2<sup>-18</sup>2<sup>-19</sup>2<sup>-20</sup>2<sup>-21</sup>2<sup>-22</sup>2<sup>-23</sup>

<h3 id="j4qGX">Scientific Notation:</h3>
                      sign                        exponent

        <font style="color:#DF2A3F;">+</font>   <font style="color:#DF2A3F;">7.125</font> x e<sup><font style="color:#DF2A3F;">10</font></sup>

1 <= valid numbers <2

<h4 id="tCbKG">So:</h4>
1. The sign bit stores the sign:	0	-->	  positive numbers

    1	    -->     negative numbers

2. The biased exponent stores the exponent.
3. The fraction stores the valid numbers.



<h3 id="wj7LS">The process of transforming a float number into the binary system:</h3>
 take the **7.125** as an example

the integer part:**0000 0111**                     the fractional part:             

                                                  0.125x2=0.25  take the integer part:0

                                                0.25x2=0.5.  take the integer part:0

             					0.5x2=1.0  take the integer part:1

             get the result:    **.001**

combine it, get: **111.001  **  

move leftward 2 bits, get: **1.11001 ** 

so the exponent is **2**

then the biased exponent equals: **127+2=129 **

<font style="color:#DF2A3F;">(tips: as the biased exponent part has no sign, set the middle number 127 as the zero</font>) 

the binary number of 129 is: 1000 0001  

so the result is:

0 <font style="color:#DF2A3F;">|</font> 1000 0001 <font style="color:#DF2A3F;">|</font> 1100 1000 0000 0000 0000 000   

