# Lab Report #5: More on Lab Report 3

I have these files to show more about the `grep` command
<br />
![fileOneText](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab5/fileOneText.png)
<br />
![fileTwoText](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab5/fileTwoText.png)
<br />
![fileThreeText](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab5/fileThreeText.png)

## `grep -w`
![grep-w](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab5/grep-w.png)
<br />
As you can see in the terminal, it gives out that there are two "apple" inside of `1.txt` and one in `2.txt`.
<br />
The `grep -w` command is to search for a specific word in a file (or couple of files)

## `grep -e`
![grep-e](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab5/grep-e.png)
<br />
The command `grep -e` is to search for multiple patterns in a file (or couple of files)
<br />
Different than the `grep -w`, the command `grep -e` will also gives out the word that contains the pattern. Such as in the screenshot, except the word "apple" is shown, the word "pineapple" is also contains in the result

## `grep -m`
![grep-m](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab5/grep-m.png)
<br />
The command `grep -m` is used to limit the number of matches returned by `grep`
<br />
By showing in the screenshot, it will give out the number of words which contains the word "apple" 
<br />
This goes by `grep -m (#the number of words wanna grep) (the word/pattern) (file name)`
