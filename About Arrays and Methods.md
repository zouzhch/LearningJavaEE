<a name="Pt32N"></a>
### Arrays
1. Two methods to declare an array
   - Dynamic declaration: `int[] nums = new int[3]`
   - Static declaration: `int[] nums = {1,2,3}`
      - can't be separated into two sentences like this: `int[] nums; nums = {1,2,3}`
2. 2-dimension arrays also have two ways of declarations:
   - Dynamic declaration: 
      - `int[][] nums = new int[3][2]`
      - if you don't want to fix the length of the sub-array, the 2nd number is allowed to be vacant: `int[][] nums = new int[3][]`, then you can assign it manually, `nums[0] = new int[3]; nums[1] = new int[5]`, so you can assign different length of arrays to this 2D array.
   - Static declaration: `int[][] nums = {{1,2},{3,5,7},{4,4,4}}`

   
<a name="JCMRf"></a>
### Method

1. `public void method(int ... nums)`

`int ... nums `represent the variable parameters:

   - can pass any quantity of variables to the parameter: 0 to any
   - it is essentially an array
   - Other non-variable parameters can be assigned before, not after.
2. `public void method(int num1, int ... nums)`

`public void method(int num1, int num2)`<br />They belong to a reload method, a special one. If you evoke this method by `method(1,2)`, the second method will be called. Evoking like this: `method(1, new int[]{2})`, thus the first method can be called.
