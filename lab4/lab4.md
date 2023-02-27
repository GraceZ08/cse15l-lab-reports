# Lab Report #4 Task From The Competition

## Step 1: Git Clone
![Step1Clone](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab4/Step1Clone.png)
<br />
Using `git clone` and the ssh link, for mine it is `git@github.com:GraceZ08/lab7.git`, to clone the file.

## Step 2: Set into the Dictionary
![Step2OpenDictionary](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab4/Step2OpenDictionary.png)
<br />
Before run the JUnit, should firstly get into the file dictionary, by using `cd lab7` to get into the file. [the `ls` is to check at which dictionary]

## Step 3: Run JUnit
![Step3JUnit](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab4/Step3JUnit.png)
<br />
Run the JUnit, using the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` which shows fail one test, and during the result, we can figure out where is the part should be fixed. `at ListExamples.merge(ListExamples.java:42)`

## Step 4: Open the File and Fix the Bug
![Step4OpenFile](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab4/Step4OpenFile.png)
<br />
By using command `nano` to open file in terminal. (press `<enter>`)
<br />
![Step5ChangeCode](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab4/Step5ChangeCode.png)
<br />
By using the arrow key `<up><down>`and `<left><right>`move the cursor to the place wanna change, and change the code, which is make `index1` to `index2`
<br />
Press `ctrl + x` to exit the file reading, then press `Y` and `enter` to save the file.
