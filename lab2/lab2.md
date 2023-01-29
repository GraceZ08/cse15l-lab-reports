# Lab Report#2 Servers and Bugs

##Part 1

##Part 2: Choosed the second one
- A failure-inducing input for the buggy program, as a JUnit test and any associated code
...
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
...
