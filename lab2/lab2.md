# Lab Report#2 Servers and Bugs

## Part 1
Based on the sample server `NumberServer`, I have the code here.
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    StringBuilder messages = new StringBuilder();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return messages.toString();
        }else{
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")){
                    messages.append("\n" + parameters[1]);
                    return messages.toString();
                }
            }
            return "404 Not Found!";
        }

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
![hello](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab2/hello.png)
![howareyou](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab2/howareyou.png)
- The method which I called to use is `handleRequest` from the class `class Handler implements URLHandler`
- The parameter is the URL "http://localhost:2000/add-message?s=..." which followed by the message we want to put in.
- I get the messege we put in, by using the "split", and store the message into a Arraylist called `addWords`.
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
- An input that doesn???t induce a failure, as a JUnit test and any associated code (Given)
```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```
![Bug](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab2/Bug.png)
- The bug, as the before-and-after code change required to fix it
- Before
```
 static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```
  - After
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
  
  ## Part 3
  - In the two weeks lab, I learned how to write a simple test case, and how to write a simple web server
  - Such as in the week 3 lab, the search engine, use some basic keyword input to acquire the result that matches users query. A few very interesting thing about simple search engine is that it???s easy to use very user friendly, the speed for a simple search engine will be more efficient then a complex search engine, and also low cost of resource usage. 
