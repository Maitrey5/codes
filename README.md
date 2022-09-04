/******************************************************************************

                              Online C++ Compiler.
               Code, Compile, Run and Debug C++ program online.
Write your code in this editor and press "Run" button to compile and execute it.

*******************************************************************************/

#include<stdio.h> 
int stack[5],top=-1,n=5;

struct node{
    int data;
    struct node *next;
};

struct node* head=NULL;
int isfull()
{
    if(top==(n-1))
    {
        return 1;
    }
    else
    {
        return 0;
    }
}

int isempty(struct node *head)
{
    if(head==NULL)
    {
        return 1;
    }
    else
    {
        return 0;
    }
}
struct node* push(struct node *head)
{
    int t;
    printf("enter the element to be pushh");
    scanf("%d",&t);
    
    top++;
    
    struct node *ptr=head;
    
    struct node *p;
    p=(struct node*)malloc(sizeof(struct node));
    p->data=t;
    p->next=ptr;
    head=p;
    return head;
    

    // int t;
    // if(isfull())
    // {
    //     printf("stack noverflow \n");
    // }
    // else
    // {
    //     printf("enter the element to be push");
    //     scanf("%d",&t);
        
        
    //     printf("\n");
        
    //     top=top+1;
    //     stack[top]=t;
    // }
}

struct node* pop(struct node *head)
{
    if(isempty(head))
    {
        printf("stack is empty");
        return head;
    }
    else
    {
        struct node *ptr=head;
        printf("popped element is %d",ptr->data);
        head=ptr->next;
        free(ptr);
        return head;
    }
}

void display(struct node *head)
{
    
        struct node *ptr=head;
        
        while(ptr->next!=NULL)
        {
            printf("%d",ptr->data);
            ptr=ptr->next;
        }
        
        printf("%d",ptr->data);
}
// void peep()
// {
//     int r;
//     printf("enter the no of element which is to be peeped");
//     scanf("%d",&r);
    
//     if((r<=top)&&(r>=0))
//     {
//     printf("peeped element =%d",stack[top-r+1]);
//     }
//     else
//     {
//         printf("no element exist");
//     }
// }
int main()
{
    int w=1,u;
    
    while(w)
    {
        printf("press 1 for push\n");
        printf("press 2 for pop\n");
        printf("press 3 for display\n");
        printf("press 4 for peep\n");
        printf("press 5 for exit\n");

        
        scanf("%d",&u);
        
        switch(u)
        {
            case 1:
            head=push(head);
            break;
            
            case 2:
            head=pop(head);
            break;
            
            case 3:
            display(head);
            break;
            
            // case 4:
            // peep();
            // break;
            
            case 5:
            u=0;
            break;
            
            default:
            break;
        }
    }
       return 0;
}



