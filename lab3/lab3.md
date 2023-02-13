# Lab Report #3 Researching Commands

## The Command I choose is `grep`

- `grep -v "pattern"`
The command `grep -v`, is used to invert the match, which will returns all the lines that do not match the pattern in the file.
![grep-v](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-v.png)
 In the first example, I choose the pattern as "and", and all the lines inside of the ch7.txt are skipped. (those empty lines are the empty lines inside of the file.)
![grep-v2](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-v2.png)
To make sure I understand the command clearly, I make a simple txt file, which only contains couple words, and that shows that all the lines contais the word "to" are skipped.

---

- `grep -i`
The "-i" option is used to perform case-insensitive searches. 
![grep-i2](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-i2.png)
In the first example, I searched in the written_2 documents, and to find the word "travel" in the file "berlitz1". The result gives the txt file name and also the lines contain the word "travel" inside of each txt file.
![grep-i](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-i.png)
The second example is the file I created by myself, makes the command shows more clear. I create different situation which contains upper-case and lower-case, in this case, it shows that by using the "-i" option can ignore the format of the word, and given out the search answer.

---

-`grep -c`
The "-c" option counts the number of lines that match the pattern searched.
![grep-c](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-c.png)
This is the one I searched in the "written_2" file. It shows how many lines are the word "the" exists in different files. For example, it shows that there are 374 lines contains the word "the" in the file "HistoryJapan.txt".
![grep-c2](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-c2.png)
Inside of the file, it can clearly shows that the "-c" option counts the line, not the total number of the word. Such as the second try in the pattern "e", it shows the result as "4", not the total number of "e" : "6".

---

-`grep -n`
The "-n" option is used to display the line number of each matching line.
![grep-n](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-n.png)
This shows that the result will contain the txt file in the folder, the line contains the pattern, and the whole line. Divided by the symbol ":"
![grep-n2](https://raw.githubusercontent.com/GraceZ08/cse15l-lab-reports/main/lab3/grep-n2.png)
Cuz it search in one certain file, didn't shows the txt file name in the result, only the line number and the line.

---
