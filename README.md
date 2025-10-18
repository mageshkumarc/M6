# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int x, y, area;
    int *ptr;

    printf("Enter the length: ");
    scanf("%d", &x);

    printf("Enter the breadth: ");
    scanf("%d", &y);

    ptr = &y;
    area = x * (*ptr);

    printf("Area of rectangle = %d\n", area);

    return 0;
}
```
## OUTPUT
		       	
<img width="311" height="171" alt="image" src="https://github.com/user-attachments/assets/68a1721d-6d78-4d51-b404-f798d66bf1d5" />


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str;

    str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    strcpy(str, "WELCOME");

    printf("%s\n", str);

    free(str);

    return 0;
}
```
## OUTPUT
<img width="221" height="122" alt="image" src="https://github.com/user-attachments/assets/657f9d19-c775-4b6b-a963-fc9e54627661" />



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct student {
    char name[50];
    int roll;
    float marks;
};

int main() {
    struct student s;

    printf("Enter name: ");
    scanf(" %[^\n]", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```

## OUTPUT
<img width="360" height="297" alt="image" src="https://github.com/user-attachments/assets/f6190374-3766-4aa5-ba71-f850ce53b304" />


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct employee {
    char name[50];
    int id;
    float basic, hra, da, gross;
};

int main() {
    struct employee e[3];
    int i;

    for (i = 0; i < 3; i++) {
        printf("Enter name of employee %d: ", i + 1);
        scanf(" %[^\n]", e[i].name);
        printf("Enter ID of employee %d: ", i + 1);
        scanf("%d", &e[i].id);
        printf("Enter basic salary of employee %d: ", i + 1);
        scanf("%f", &e[i].basic);

        e[i].hra = e[i].basic * 0.10;
        e[i].da = e[i].basic * 0.05;
        e[i].gross = e[i].basic + e[i].hra + e[i].da;
    }

    printf("\nEmployee Details:\n");
    for (i = 0; i < 3; i++) {
        printf("Name: %s\n", e[i].name);
        printf("ID: %d\n", e[i].id);
        printf("Gross Salary: %.2f\n\n", e[i].gross);
    }

    return 0;
}
```

 ## OUTPUT

 <img width="480" height="706" alt="image" src="https://github.com/user-attachments/assets/5cc5cf7b-809d-493b-945d-858b14b2f67b" />


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
};

int main() {
    struct student s[2];
    int i, j;

    for (i = 0; i < 2; i++) {
        printf("Enter marks for student %d:\n", i + 1);
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
    }

    for (i = 0; i < 2; i++) {
        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
    }

    for (i = 0; i < 2; i++) {
        printf("Total marks of student %d: %d\n", i + 1, s[i].total);
        printf("Average marks of student %d: %.2f\n", i + 1, s[i].total / 5.0);
    }

    return 0;
}
```

## OUTPUT

 <img width="382" height="331" alt="image" src="https://github.com/user-attachments/assets/ee1ed96b-d8a3-44ae-b3b5-5d76d38ebc78" />


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


