# Lab Report#2 Servers and Bugs

##Part 1

##Part 2: Choosed the second one
- A failure-inducing input for the buggy program, as a JUnit test and any associated code
```
@Test
    public void testReversedII(){
      int[] input1 = {1,2,3,4 };
      assertArrayEquals(new int[]{ 4,3,2,1}, ArrayExamples.reversed(input1));
  }

  @Test
    public void testReversedIII(){
        int[] inputIII = {1};
        assertArrayEquals(new int[]{1},ArrayExamples.reversed(inputIII));
  }

  @Test
    public void testReversedIV(){
        int[] intputIV = {1,2,3};
        assertArrayEquals(new int[]{3,2,1},ArrayExamples.reversed(intputIV));
```
-An input that doesn’t induce a failure, as a JUnit test and any associated code (Given)
```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```
![Bug](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab2/Bug.png)
-The bug, as the before-and-after code change required to fix it
-Before
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```
  -After
  ```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length/2; i += 1) {
      newArray[i] = arr[arr.length - i -1];
      newArray[arr.length - i - 1] = arr[i];
    }
    if(arr.length % 2 != 0){
      newArray[arr.length/2] = arr[arr.length/2];
    }
    if(arr.length < 2){
      return arr;
    }
    return newArray;
  }
  ```
  
