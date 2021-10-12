NATIONAL INSTITUTE OF TECHNOLOGY, SILCHAR;
DATA STRUCTURES;
ASSIGNMENT-1;
COURSE CODE-CS 201;
Name-Shamimah Sabnoor;
Roll No.-2012034;
Section-A;

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



Write a C program to benchmark the performance of Selection Sort and Bubble Sort. Total input
items may be randomly generated and already sorted. You have to tell your story using the bar chart
as given below for an example.



#include <stdio.h>
#include <stdlib.h>
#include <time.h>

//*********************************************FOR WORST CASE**********************************************************//
void swap(int *v, int *s)
{
  int temp=* v;
  *v=*s;
  *s=temp;
}


// A function to implement bubble sort
void bubbleSort(int arr[], int n)
{
   int i, j;
   for (i = 0; i < n-1; i++)     
 
       for (j = 0; j < n-i-1; j++)
           if (arr[j] > arr[j+1])
           {
              swap(&arr[j], &arr[j+1]);
           }
}
  
void selection(int arr[], int n)
{
  int i, j, min_idx;
  for (i = 0; i<n-1;i++)
   {
     min_idx=i;
      for(j=i+1;j<n;j++)
           if(arr[j]<arr[min_idx])
               min_idx=j;
          swap(&arr[min_idx],&arr[i]);
   }
}

void insertion(int arr[], int n)
{
    int i,key,j;
    for (i =1; i<n;i++)
    {
      key =arr[i];
        j=i-1;
         while (j= 0 && arr[j]>key)
         {
             arr[j+1]=arr[j];
              j=j-1;
         }
       arr[j+1]=key;
        
    }
}

int main()
{ 
    //worst complexity
clock_t t;
int i, j, n=10000;
srand(time(NULL));
double mt;
int arr[n];

//for input
for(i=0,j=n;i<n;i++,j--)
{
 arr[i]=j;
}

//for bubble sorttime
   t=clock();
   bubbleSort(arr,n);
   t=clock()-t;
   mt=((double)t)/CLOCKS_PER_SEC;
   
   printf("bubblesort() took %f  seconds to execute\n", mt);
   
    for(i=0,j=n; i<n; i++,j--)
    {
    arr[i]=j;
    }
    
//for selection sort time
    t = clock();
    selection(arr, n);
    t =clock()-t;
    mt =((double)t)/CLOCKS_PER_SEC;
    printf("selectionsort() took %f seconds to execute \n",mt);
    printf("\n");
    
    for(i=0, j=n;  i<n; i++, j--)
    {
        arr[i]=j;
    }
//for insetion sort time
  t =clock();
   insertion(arr, n); 
   t=clock()-t;
   mt =((double)t)/CLOCKS_PER_SEC;
   printf("insetionsort() took %f seconds to execute \n", mt);
   return 0;
   
   }

   //****************************************************FOR BEST CASE***********************************************//
   //*********************************** COMMENT OUT THE ABOVE CODE TO RUN THIS ***************************************//
      
void swap(int *v, int *s)
{
  int temp=* v;
  *v=*s;
  *s=temp;
}

void bubble(int arr[], int n)
{
    int i, j;
    int swapped;
    for (i = 0; i < n - 1; i++)
    {
        swapped = 0;
        for (j = 0; j < n - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                swap(&arr[j] ,&arr[j + 1]);
                swapped = 1;
            }
        }
        if (swapped == 0)
            break;
    }
}
void selection(int arr[], int n)

{
    int i, j, min_idx;
    for (i = 0; i< n - 1; i++)
    {
        min_idx = i;
        for (j = i + 1; j < n; j++)
            if (arr[j] <arr[min_idx])
                min_idx = j;
        swap(&arr[min_idx], &arr[i]);
    }
}
void insertion(int arr[], int n)
{
    int i, key, j;
    for (i = 1; i < n; i++)
    {
        key = arr[i];
        j = i - 1;
        while (j >= 0 && arr[j] > key)
        {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}
int main()
{ 
    //for best time complexity
    clock_t t;
    int i, n = 10000;
    srand(time(NULL));
    double mt;
    int arr[n];


    //for input
    for (i = 0; i < n; i++)
    {
        arr[i] = i + 10000;
    }


    //for bubble sort time
    t = clock();
    bubble(arr, n);
    t = clock() - t;
    mt = ((double)t) / CLOCKS_PER_SEC;
    printf("bubblesort() took %f seconds to execute  \n", mt);
    
    for (i = 0; i < n; i++)
    {
        arr[i] = i + 10000;
    }


    //for selection sort time
    t = clock();
    selection(arr, n);
    t = clock() - t;
    mt = ((double)t) / CLOCKS_PER_SEC;
    printf("selectionsort() took %f seconds to execute \n", mt);
    for (i = 0; i < n; i++)
    {
        arr[i] = i + 10000;
    }

    //for insetion sort time
    t = clock();
    insertion(arr, n);
    t = clock() - t;
    mt = ((double)t) / CLOCKS_PER_SEC;
    printf("insetionsort() took %f seconds to execute \n ", mt);
    return 0;
}



   //****************************************************FOR AVERAGE CASE***********************************************//
   //*********************************** COMMENT OUT THE ABOVE CODE TO RUN THIS ***************************************//
      
void bubble(int arr[], int n)
{
    int i, j;
    for (i = 0; i < n - 1; i++)
    {
        for (j = 0; j < n - i - 1; j++)
        {

    if (arr[j] > arr[j + 1])
                swap( &arr[j], &arr[j + 1]);
        }
    }
}
void selection(int arr[], int n)
{
    int i, j, min_idx;
    for (i = 0; i < n - 1; i++)
    {
        min_idx = i;
        for (j = i + 1; j < n; j++)
            if (arr[j] < arr[min_idx])
                min_idx = j;
        swap(&arr[min_idx], &arr[i]);
    }
}
void insertion(int arr[], int n)
{
    int i, key, j;
    for (i = 1; i < n; i++)
    {
        key = arr[i];
        j = i - 1;
        while (j = 0 && arr[j] > key)
        {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}

int main()
{
    clock_t t;
    int i, n = 10000;
    srand(time(NULL));
    double mt;
    int arr[n];


    //for input
    for (i = 0; i < n; i++)
    {
        arr[i] = rand();
    }

//for bubble sort time
    t = clock();
    bubble(arr, n);
    t = clock() - t;
    mt = ((double)t) / CLOCKS_PER_SEC;
    printf("bubblesort() took %f seconds to execute \n ", mt);
    for (i = 0; i < n; i++)
    {
        arr[i] = rand();
    }


    //for selection sort time
    t = clock();
    selection(arr, n);
    t = clock() - t;
    mt = ((double)t) / CLOCKS_PER_SEC;
    printf("selectionsort() took %f seconds to execute \n ", mt);
    for (i = 0; i < n; i++)
    {
        arr[i] = rand();
    }


    //for insetion sort time
    t = clock();
    insertion(arr, n);
    t = clock() - t;
    mt = ((double)t) / CLOCKS_PER_SEC;
    printf("insetionsort() took %f seconds to execute \n ", mt);

    return 0;
}
