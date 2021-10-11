NATIONAL INSTITUTE OF TECHNOLOGY, SILCHAR
DATA STRUCTURES,
ASSIGNMENT-1
COURSE CODE-CS 201
Name-Shamimah Sabnoor
Roll No.-2012034
Section-A

QUESTION:
1.Write a C compiler to check whether a given number is a valid floating point number or not. Write
for all possible all test cases. Example:
input: 2.0
output: valid
input: 1.
output: invalid

#include<stdio.h>
#include<conio.h>
#include<string.h>
int main()
{
    char number[50];
    int flag=0;
    int length, i=0;
    printf("enter a number");
    scanf("%s",&number);
    length=strlen(number);
    while(number[i++]!='\0')
    {
        if(number[i]=='.')
        {
            flag=1;
            break;

    }
    }
    if(flag)
        printf("enter number is a valid float number");
    else
        printf("enter number is invalid");
    return 0;
}


2.Write a C program to check whether a given email is valid or not. Rules of email ID can be refer to
the link https://en.wikipedia.org/wiki/Email_address

#include<stdio.h>
main()
{
    char mailid[50];
    int i,p1,p2;
    p1=p2=0;
    printf("enter your mailid:");
    scanf("%s",&mailid);
    for(i=0;mailid[i]!='\0';i++)

     {

       if
        (mailid[i]=='@')
           p1=i;
        if
        (mailid[i]=='.')
        p2=i;
     }



    if (p1>3 && (p2-p1)>3)
        printf("valid email id");
    else
        printf("invalid email id");
        printf("\n");

    return 0;
}


3.Let us assume that A is a single dimensional array. You have given A array to construct a two-
dimensional array. Write a C program to convert explicitly from 2D array to 1D array. Example,

Map(A, i, j) gives you A[i][j]. You can use either row-major order or column-major order.

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main()
{
	int arr2D[10][10], * arr1D;
	int n, m, i, j;

	#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main()
{
	int arr2D[10][10], * arr1D;
	int n, m, i, j;


	printf("Enter Number of Rows: ");
	scanf("%d", &n);
	printf("Enter Number of columns: ");
	scanf("%d", &m);

	printf("Enter 2D Array: \n");
	for (i = 0; i < n; ++i) {
		for (j = 0; j < m; ++j) {
			scanf("%d", &arr2D[i][j]);
		}
	}


	arr1D = (int*)malloc(n * m * sizeof(int));

	for (i = 0; i < n; ++i) {
		for (j = 0; j < m; ++j) {
			// mapping 1D array to 2D array
			arr1D[i * m + j] = arr2D[i][j];
		}
	}

	printf("1D Array: ");

	for (i = 0; i < n * m; ++i) {
		printf("%d ", arr1D[i]);
	}

}
	printf("Enter Number of Rows: ");
	scanf("%d", &n);
	printf("Enter Number of columns: ");
	scanf("%d", &m);

	printf("Enter 2D Array: \n");
	for (i = 0; i < n; ++i) {
		for (j = 0; j < m; ++j) {
			scanf("%d", &arr2D[i][j]);
		}
	}


	arr1D = (int*)malloc(n * m * sizeof(int));

	for (i = 0; i < n; ++i) {
		for (j = 0; j < m; ++j) {

			arr1D[i * m + j] = arr2D[i][j];
		}
	}

	printf("1D Array: ");

	for (i = 0; i < n * m; ++i) {
		printf("%d ", arr1D[i]);
	}
	return 0;
}
