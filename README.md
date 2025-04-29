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

```c
#include <stdio.h>

int main(void)
{
    float length, width, area;
    float *ptr_length = &length;
    float *ptr_width = &width;

    printf("Enter length of rectangle: ");
    scanf("%f", ptr_length);
    
    printf("Enter width of rectangle: ");
    scanf("%f", ptr_width);

    area = (*ptr_length) * (*ptr_width);

    printf("Area of rectangle: %.2f\n", area);

    return 0;
}
```

## OUTPUT
		       	
![image](https://github.com/user-attachments/assets/529efc02-fa9f-449f-925b-e9f8b6e9d15b)


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

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(void)
{
    char *str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    strcpy(str, "WELCOME");
    printf("%s\n", str);

    free(str);
    str = NULL;

    return 0;
}
```

## OUTPUT

![image](https://github.com/user-attachments/assets/57f80d6a-9da4-4674-8fe5-94e39512b1bb)


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

```c
#include <stdio.h>

struct Student {
    char name[50];
    int roll;
    float marks;
};

int main(void)
{
    struct Student s;

    printf("Enter student name: ");
    scanf("%49s", s.name);
    
    printf("Enter roll number: ");
    scanf("%d", &s.roll);
    
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll: %d\n", s.roll);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```

## OUTPUT

![image](https://github.com/user-attachments/assets/673348cf-8a91-41b4-bccb-47568b1956b8)

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

```c
#include <stdio.h>

struct Employee {
    char name[50];
    int id;
    float basic;
    float hra;
    float da;
    float gross;
};

int main(void)
{
    struct Employee emp[3];

    for(int i = 0; i < 3; i++) {
        printf("\nEnter details for employee %d:\n", i+1);
        printf("Name: ");
        scanf("%49s", emp[i].name);
        printf("ID: ");
        scanf("%d", &emp[i].id);
        printf("Basic Salary: ");
        scanf("%f", &emp[i].basic);
        printf("HRA: ");
        scanf("%f", &emp[i].hra);
        printf("DA: ");
        scanf("%f", &emp[i].da);

        emp[i].gross = emp[i].basic + emp[i].hra + emp[i].da;
    }

    printf("\nEmployee Payroll:\n");
    for(int i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i+1);
        printf("Name: %s\n", emp[i].name);
        printf("ID: %d\n", emp[i].id);
        printf("Basic: %.2f\n", emp[i].basic);
        printf("HRA: %.2f\n", emp[i].hra);
        printf("DA: %.2f\n", emp[i].da);
        printf("Gross Salary: %.2f\n", emp[i].gross);
    }

    return 0;
}
```

 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/21937bcb-75b2-4508-9945-def5066756f7)


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

```c
#include <stdio.h>

struct Student {
    char name[50];
    int rollno;
    int subjects[5];
    int total;
    float average;
};

int main(void) {
    struct Student s[2];

    for(int i = 0; i < 2; i++) {
        printf("\nEnter details for student %d:\n", i+1);
        printf("Name: ");
        scanf("%49s", s[i].name);
        printf("Roll number: ");
        scanf("%d", &s[i].rollno);

        printf("Enter marks for 5 subjects:\n");
        for(int j = 0; j < 5; j++) {
            scanf("%d", &s[i].subjects[j]);
        }
    }

    for(int i = 0; i < 2; i++) {
        s[i].total = 0;
        for(int j = 0; j < 5; j++) {
            s[i].total += s[i].subjects[j];
        }
        s[i].average = s[i].total / 5.0f;
    }

    printf("\nStudent Results:\n");
    for(int i = 0; i < 2; i++) {
        printf("\nStudent %d:\n", i+1);
        printf("Name: %s\n", s[i].name);
        printf("Roll No: %d\n", s[i].rollno);
        printf("Total Marks: %d\n", s[i].total);
        printf("Average Marks: %.2f\n", s[i].average);
    }

    return 0;
}
```

## OUTPUT

 ![image](https://github.com/user-attachments/assets/8e84a525-15d7-43aa-b773-31065847d60e)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


