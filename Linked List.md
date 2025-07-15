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
## 3.Adding an employee node at the end of the linked list
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
void Addnodeattail(int a){
        struct node *pretrav,*new;
        new=(struct node*)malloc(sizeof(struct node));
        if(new==NULL){
                printf("malloc error");
                return;
        }
        new->val=a;
        new->nxt=NULL;
        if(phead==NULL){
                phead=new;
        }
        else{
                pretrav=phead;
                while(pretrav->nxt!=NULL){
                     pretrav=pretrav->nxt;
                }
                pretrav->nxt=new;
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
        Addnodeattail(60);
        display();
}
```
## 4. Adding an employee node at the beginning of the linked list.
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
void Addingnodeathead(int a){
        struct node *new;
        new=(struct node*)malloc(sizeof(struct node));
        if(new==NULL){
                printf("Malloc error");
                return;
        }
        new->val=a;
        new->nxt=phead;
        phead=new;
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
        Addingnodeathead(60);
        display();
}
```
## 5.Delete a node at the end of the Linked list.
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
void deletenodeatend(){
        struct node *pretrav,*trav;
        trav=phead;
        while(trav->nxt!=NULL){
                pretrav=trav;
                trav=trav->nxt;
        }
        free(trav);
        pretrav->nxt=NULL;
        trav=NULL;
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
        deletenodeatend();
        display();
}
```
## 6.Delete a node at the beginning of the Linked list.
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
void deletenodeathead(){
        struct node *ptemp;
        ptemp=phead;
        phead=phead->nxt;
        free(ptemp);
        ptemp=NULL;
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
        deletenodeathead();
        display();
}
```

