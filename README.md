Experiment-7

7.write a c program to simulate sequencial file allocation 

strategy.

Aim:

 To write a source code of the c program for simulate sequencial 

file allocation strategy.

 Program:

#include <stdio.h>

#include <stdlib.h>

#define MAX_BLOCKS 100

int main() {

int file_size, block_size, num_blocks, blocks[MAX_BLOCKS], i;

// Get input from user

printf("Enter file size: ");

scanf("%d", &file_size);

printf("Enter block size: ");

scanf("%d", &block_size);

// Calculate number of blocks needed

num_blocks = file_size / block_size;

if (file_size % block_size != 0) {

num_blocks++;

}
// Allocate blocks sequentially

for (i = 0; i < num_blocks; i++) {

blocks[i] = i;

}

// Print allocated blocks

printf("Allocated blocks: ");

for (i = 0; i < num_blocks; i++) {

printf("%d ", blocks[i]);

}

printf("\n");

return 0;

}

Output:

Enter file size:100

Enter block size:25

Allocated blocks:0 1 2 3



LRU

write a c program to simulate LRU(least recently used) page replacement algorithm. 

Aim: 

        To write a source code of the c program for simulate LRU page replacement algorithm. 

Program: 

#include<stdio.h> 

#include<conio.h> 

int fr[3];

void main()

{

    void display();

    int p[12]={7,0,1,2,0,3,0,4,2,3,0,3},i,j,fs[3]; 

    int index,k,l,flag1=0,flag2=0,pf=0,frsize=3; 

    

    for(i=0;i<3;i++)

    {

        fr[i]=-1;

    }

    for(j=0;j<12;j++)

    {

        flag1=0,flag2=0;

        for(i=0;i<3;i++)

        {

            if(fr[i]==p[j])

            {

                flag1=1;

                flag2=1;

                break;

            }

        }

        if(flag1==0)

        {

            for(i=0;i<3;i++)

            {

                if(fr[i]==-1)

                {

                    fr[i]=p[j];

                    flag2=1;

                    break;

                }

            }

        }

        if(flag2==0)

        {

            for(i=0;i<3;i++)

            fs[i]=0; 

            for(k=j-1,l=1;l<=frsize-1;l++,k--)

            {

                for(i=0;i<3;i++)

                {

                    if(fr[i]==p[k])

                    fs[i]=1;

                }

            }

            for(i=0;i<3;i++)

            {

                if(fs[i]==0)

                index=i;

            }

            fr[index]=p[j];

            pf++;

        }

        display();

    }

    printf("\n no of page faults :%d",pf); 

    getch();

}

void display()

{

    int i;

    printf("\n");

    for(i=0;i<3;i++)

    printf("\t%d",fr[i]);

}



Output: 

7     -1       -1 

7       0       -1 

7       0        1 

2       0        1 

2       0        1  

2       0        3  

2       0        3 

4       0        3 

4       0        2 

4       3        2 

0       3        2 

0       3        2 

no of page faults :6
