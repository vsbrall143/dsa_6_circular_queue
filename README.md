# dsa_6_circular_queue
circular queue



#include <stdio.h>
#include <stdlib.h>
#define MAX 5
int queue[MAX];
int front = 0;
int rear = -1;
int x;

void enqueue(int x)
{

    if (rear == MAX - 1)
    {
        printf("Queue Overflow Condition");
    }
    else
    {
        rear=(rear+1)%MAX;
        queue[rear] = x;
    }
}
void dequeue()
{
    if (front > rear)
    {
        printf("\n\n\n***Queue Underflow Condition***\n\n\n");
    }
    else
    {
        printf("  \n \n the dequeued element is %d \n", queue[front]);
        front=(front+1)%MAX;
    }
}

void display()
{
    int i;
    if (front > rear)
    {
        printf(" \n ***Queue is Empty*** \n \n");
    }
    else
    {
        printf("\n \n ***The Queue elements are*** \n");
        for (i = front; i < rear + 1; i++)
        {
            printf("%d ", queue[i]);
            printf("\n \n");
        }
    }
}

int main()
{
    int input;
    while(input!=4)
    {
        printf("<<<<<Main Menu>>>>>\n");
        printf("Enter the following choice\n");
        printf("1:Insert\t2:Delete\t3:Display\t4:Exit\n");
        scanf("%d", &input);
        switch (input)
        {
        case 1:
            printf("Enter the element you want to insert\n");
            scanf("%d", &x);
            enqueue(x);
            break;
        case 2:
            dequeue();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
            break;
        default:
            printf("Invalid Input");
        }
    }
}
