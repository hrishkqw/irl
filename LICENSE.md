// Online C compiler to run C program online
#include <stdio.h>
#include<stdlib.h>
struct node{
    int data;
    struct node *next;
};
// display

struct node *display(struct node *ptr){
    printf("enter linklist\n");
    while(ptr!=NULL){
        printf("%d ",ptr->data);
        ptr=ptr->next;
    }
    
}
// insert newnode at front
struct node *createf (struct node *ptr){
struct node *newnode;
int num;
printf("enter data ");
scanf("%d",&num);
 newnode=(struct node*)malloc(sizeof(struct node));
 newnode->data=num;
 newnode->next=ptr;
 ptr=newnode;
 return ptr;

}



// creating link list
 struct node *create(struct node *head){
     struct node *newnode, *ptr=head;
     int num;
     printf("enter -1 to end\n");
     printf("1: enter the data: ");
     scanf("%d",&num);
     
     while(num!=-1){
         newnode=(struct node*)malloc(sizeof(struct node));
         newnode->data=num;
         newnode->next=NULL;
         
         if(head==NULL){
             head=newnode;
         }else{
             ptr=head;
             while(ptr->next!=NULL){
                 ptr=ptr->next;
             }
             ptr->next=newnode;
         }
         printf("enter the data: ");
         scanf("%d",&num);
     }
 return head;
     
 }


int main() {
    int option;
 struct node *head =NULL;
 do{  printf("1: to create linklist\n");
 printf("2: to insert front\n");
 printf("3: to display\n");
 
     printf("enter your option");
     scanf("%d",&option);
     
     switch(option){
         case 1:
         head = create(head);
         printf("create linklist. \n");
         break;
         case 2:
         head= createf(head);
         printf("insert front\n");
         break;
         case 3:
          head = display(head);
         break;
     }
 }
 while(option!=11);
 

    return 0;
}
