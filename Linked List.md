## 1.Creation of a single node.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
int main(){
        phead=(struct node*)malloc(sizeof(struct node));
        phead->val=10;
        phead->nxt=NULL;
        printf("%d",phead->val);
}
```
## 2.Create 5 nodes using Linked List.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void createnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("Malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        createnode(10);
        createnode(20);
        createnode(30);
        createnode(40);
        createnode(50);
        display();
}
```
