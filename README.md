# students grade

The aim of this exercise is to process a file containing marks for a university module. The
input file will have the format

5 30
1991111 65.5 45.5
2031234 75.5 68
2012345 33 50
2019734 55.5 51.5
2187345 39 47.5

The first line of the file contains the number of students and the percentage coursework
weighting, e.g. the 30 in this example denotes that the coursework comprises 30% of the
overall module mark (with the exam making up the other 70%).

Each subsequent line contains (in order) a registration number, an exam mark and a
coursework mark. The number of such lines will match the number of students.
Write a program that will open such a file, read the first line and create a 2-dimensional
NumPy array where number of rows is the number of students and each row has 4
elements. (Initialise this array using a call to the array function with an argument
[[0,0,0,0]]*n, where nis the number of students.)

The program should then read the remaining lines line-by-line and use the input values to
store in a row of the array the registration number, the exam mark, the coursework mark
and the overall mark (calculated using the exam mark, the coursework mark and the
weighting). You may assume that all lines will contain the correct number of marks and
the number of students will match the number specified on the first line.

Having generated the array, the program should then create a 1-dimensional array with n
elements, but with a structured date type with 4 integers and one string as the
components). (Use a list containing multiple copies of a structure with default values (e.g.
zeroes and an empty string) as the argument to array.)

From the data in each row of the first array the program should generate a structure
containing the student's registration number, exam mark, coursework mark and total
mark, all rounded to the nearest integer, and a grade string to be calculated using the rules
below and store this in the corresponding element in the second array. (You can round a
real number n to the nearest integer using round(n).)

The program should then produce a version of the second array sorted by overall mark
and output this array to a file (using a single call to the print function of the form
print(array2, file=f)).

It should finally output to the screen/console the number of students who have first,
second and third-class marks, the number of students who have failed and the registration
numbers of the students who have failed.


Rules for calculating grades
Any student with a rounded mark of less than 40 for either the coursework or the exam has failed,
irrespective of the overall module mark. For all other students a rounded overall mark of 70 or more has
a first-class grade, a rounded mark between 50 and 69 (inclusive) has a second-class grade, a rounded
mark between 40 and 49 has a third-class grade, and a rounded mark below 40 fails.
