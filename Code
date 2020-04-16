#include<stdio.h>
#include<stdlib.h>
#define OK 1
#define ERROR 0
#define OVERFLOW -2
typedef int Status;

struct node{
int data;
struct node* next;
}*Lnode;

struct node* L;

void Create(int n);
void Display();
int Locate(int f);
int Insert(int data,int pos);
int Delete(int pos);
void main()
{
    int ch,n,pos,f,Plc,in;
    while(1)
    {
        printf("\n\n************************************\n");
        printf("*  Lab 1 by Nishith (10460348058)  *\n");
        printf("************************************\n");
        printf("*    Choose 1-6                    *\n");
        printf("*   1.Create a list                *\n");
        printf("*   2.Display all elements         *\n");
        printf("*   3.Search an element            *\n");
        printf("*   4.Insert a node                *\n");
        printf("*   5.Delete node                  *\n");
        printf("*   6.Exit                         *\n");
        printf("*                                  *\n");
        printf("************************************\n");


        printf(" Enter your choice: ");
        scanf("%d",&ch);
        printf("\n");

        switch(ch)
        {
        case 1:
            printf(" Enter the number of nodes : ");
            scanf("%d", &n);
            Create(n);
            printf("\n List created successfully");
            break;
        case 2:
            printf("************************\n");
            printf("The Current List is:: \n");
            Display();
            break;
        case 3:
            printf(" Enter the element to be searched : ");
            scanf("%d",&f);
            Plc=Locate(f);
            if(Plc<=n)
                printf(" Element found at node %d \n\n",Plc);
            else
                printf(" This element does not exists in linked list.\n\n");
            break;
        case 4:
            printf("\n Input data to insert in the list : ");
            scanf("%d", &in);
            printf(" Input the position to insert new node : " );
            scanf("%d", &pos);
            if(pos<=1 || pos>=n)
            {
                printf("\n Insertion can not be possible in that position.\n ");
            }
            if(pos>1 && pos<n)
            {
              Insert(in, pos);
              printf("\n Insertion completed successfully.\n ");
              n++;
            }
            break;
        case 5:
            printf("\n Input the position of node to delete : ");
            scanf("%d", &pos);

            if(pos<=1 || pos>n)
            {
                printf("\n Deletion can not be possible from that position.\n ");
            }
            if(pos>1 && pos<=n)
            {
                printf("\n Deletion completed successfully.\n ");
                Delete(pos);
            }

            break;
        case 6:
            exit(1);
        default: printf("Invalid input\n\n");
            }
    }

}
void Create(int n)
{
    struct node* temp,*p;
    int data,i;
    Lnode=(struct node*)malloc(sizeof(struct node));

    if(Lnode==NULL)
    {
        printf("Memory can not be allocated");
    }
    else
    {
        printf(" Input data for node 1 : ");
        scanf("%d", &data);
        Lnode->data = data;
        Lnode->next = NULL;
        temp = Lnode;

        for(i=2; i<=n; i++)
        {
            p = (struct node*)malloc(sizeof(struct node));
            if(p == NULL)
            {
                printf(" Memory can not be allocated.");
                break;
            }
            else
            {
                printf(" Input data for node %d : ", i);
                scanf(" %d", &data);

                p->data = data;
                p->next = NULL;

                temp->next = p;
                temp = temp->next;
            }
        }
    }
}
void Display()
{
    struct node* temp;
    if(Lnode == NULL)
    {
        printf(" List is empty.");
    }
    else
    {
        temp = Lnode;
        while(temp != NULL)
        {
            printf(" Data = %d\n", temp->data);
            temp = temp->next;
        }
    }
}
int Locate(int f)
{
    int pointer=1;
    L=Lnode;
	while(L->next!=NULL)
	{
		if(L->data==f)
			break;
		else
			pointer++;
			L=L->next;
	}
	return pointer;
}

int Insert(int data,int pos)
{
    int i;
    struct node* temp, *p;
    p = (struct node*)malloc(sizeof(struct node));
    if(p == NULL)
    {
        printf(" Memory can not be allocated.");
    }
    else
    {
        p->data = data;
        p->next = NULL;
        temp = Lnode;
        for(i=2; i<=pos-1; i++)
        {
            temp = temp->next;

            if(temp == NULL)
                break;
        }
        if(temp != NULL)
        {
            p->next = temp->next;
            temp->next = p;
        }
        else
        {
            printf(" Insert is not possible to the given position.\n");
        }
    }

}

int Delete(int pos)
{
    int i;
    struct node* temp, *pre;

    if(Lnode == NULL)
    {
        printf(" There are no nodes in the List.");
    }
    else
    {
        temp = Lnode;
        pre = Lnode;

        for(i=2; i<=pos; i++)
        {
            pre = temp;
            temp = temp->next;

            if(temp == NULL)
                break;
        }
        if(temp != NULL)
        {
            if(temp == Lnode)
                Lnode = Lnode->next;

            pre->next = temp->next;
            temp->next = NULL;
            free(temp);
        }
        else
        {
            printf(" Deletion can not be possible from that position.");
        }
    }

}
