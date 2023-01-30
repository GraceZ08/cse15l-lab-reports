# Lab Report#2 Servers and Bugs

## Part 1
Based on the sample server `NumberServer`, I have the code here.
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> addWords = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Add a String";
        }else{
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                addWords.add(parameters[1]+"\n");
                return String.valueOf(addWords);
            }

        }
        return "404 Not Found!";
    }
}


public class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
![addHello](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab2/addHello.png)
![addHowAreYou](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab2/addHowAreYou.png)
## Part 2: Choosed the second one
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
  - Bugs: incorrect bounds in for loop; incorrect array in return statement
  - Changes: make the bound half of the array(those special cases analyzed by other if statement); Assigned the value to new array.
  
  ## Part3
  -In the two weeks lab, I learned how to write a simple test case, and how to write a simple web server.
