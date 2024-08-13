### Reverse Code And Complement Code
First, we should know what is the **reverse code**:

- the reverse code of positive numbers is itself
- the reverse code of negative numbers is getting the reverse of all the bites except for the first bit

for example:

| Decimal Number | Binary Number | Reverse Code |
| --- | --- | --- |
| -64 | 1100 0000 | 1011 1111 |

Then the definition of the **complement code** is:

- the complement code of positive numbers is itself
- the complement code of negative numbers is the reverse code of itself plus 1

for example:

| Decimal Number | Binary Number | Reverse Code | Complement Code |
| --- | --- | --- | --- |
| -64 | 1100 0000 | 1011 1111 | 1100 0000 |


---

### The Storage In the Computer

- Use the first bit to represent the sign bit in the computer.
- All the numbers are stored in the computer according to the complement form, consider the condition when we store a number by the original binary number, if question the result of -1 + 1, in the binary mode, means: 1000 0001 + 0000 0001, then get the result: 1000 0010, transform it to a decimal number, then get the result: -2. It is clearly incorrect based on common sense.
- But it's right in the complement code mode, like this:
| Decimal Number | Binary Number | Reverse Code | Complement Code |
| --- | --- | --- | --- |
| -1 | 1000 0001 | 1111 1110 | 1111 1111 |
| 1 | 0000 0001 | 0000 0001 | 0000 0001 |
| 0 | (transformed from reverse code):<br />0000 0000 | (transformed from complement):<br />1111 1111 | (1)0000 000 |

- So there are 127 numbers in the complement code from 1111 1111 to 1000 0001, and we don't use 1000 0000 equals to -0 which has no meaning. Still, there are definitely 128 numbers in the negative number, so the relative organisation assigned the complement code 1000 0000 to the decimal number -128 as the minimum value of negative numbers.
