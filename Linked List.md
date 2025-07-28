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
## 7.Insertion of node at a particular position of the Linked list.
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
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt != NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void insertnode(int d,int x){
        struct node *ptrav,*pnew;
        ptrav=phead;
        while(ptrav!=NULL){
                if(ptrav->val==x){
                   pnew=(struct node*)malloc(sizeof(struct node));
                   if(pnew==NULL){
                       printf("Malloc error");
                       return;
                    }
                   pnew->val=d;
                   pnew->nxt=ptrav->nxt;
                   ptrav->nxt=pnew;
                   ptrav=pnew;
                }
                else{
                        ptrav=ptrav->nxt;
                }

        }
}
void display(){
        struct node *ptemp;
        ptemp=phead;
        while(ptemp!=NULL){
                printf("%d ",ptemp->val);
                ptemp=ptemp->nxt;
        }
}
int main(){
        int n,data,in,x;
        printf("Enter the total number of nodes: ");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the data in the node:");
                scanf("%d",&data);
                createnode(data);
        }
        printf("Enter the insertion value:");
        scanf("%d",&in);
        printf("Enter the target");
        scanf("%d",&x);
        insertnode(in,x);
        printf("The elements in the list are:");
        display();
}
```
## 8.Insertion of node at a middle position of the Linked list.
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
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt != NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void middlenodeinsertion(int d){
    struct node *pnew,*prev,*slow,*fast;
    slow=fast=phead;
    pnew=(struct node*)malloc(sizeof(struct node));
    if(pnew==NULL){
            printf("malloc error");
            return;
    }
    pnew->val=d;
    pnew->nxt=NULL;
    while(fast!=NULL&&fast->nxt!=NULL){
            prev=slow;
            slow=slow->nxt;
            fast=fast->nxt->nxt;
    }
    pnew->nxt=prev->nxt;
    prev->nxt=pnew;
    return;
}
void display(){
        struct node *ptemp;
        ptemp=phead;
        while(ptemp!=NULL){
                printf("%d ",ptemp->val);
                ptemp=ptemp->nxt;
        }
}
int main(){
        int n,data,in,x;
        printf("Enter the total number of nodes: ");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the data in the node:");
                scanf("%d",&data);
                createnode(data);
        }
        printf("Enter the insertion value:");
        scanf("%d",&in);
        middlenodeinsertion(in);
        printf("The elements in the list are:");
        display();
}
```
## 9.Deletion of middle node using Linked list.
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
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}
void deletenode(){
        struct node *prev,*slow,*fast,*temp,*pnew;
        slow=fast=phead;
        if(phead==NULL||phead->nxt==NULL){
                printf("It have 0 or 1 node");
                return;
        }
        while(fast!=NULL&&fast->nxt!=NULL){
                prev=slow;
                slow=slow->nxt;
                fast=fast->nxt->nxt;
        }
        temp=prev->nxt;
        prev->nxt=prev->nxt->nxt;
        free(temp);
}
int main(){
        int n,data;
        printf("Enter total number of nodes:");
        scanf("%d",&n);
        printf("Enter the values of the nodes:");
        for(int i=0;i<n;i++){
                printf("Enter the value at node");
                scanf("%d",&data);
                createnode(data);
        }
        deletenode();
        display();
}
```
## 10.Reversing of linked list.
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
void reverse(){
        struct node *prev=NULL,*current=phead,*temp=NULL;
        while(current!=NULL){
                temp=current->nxt;
                current->nxt=prev;
                prev=current;
                current=temp;
        }
        phead=prev;
}
void display(){
        struct node *temp=phead;
        while(temp!=NULL){
                printf("%d\n",temp->val);
                temp=temp->nxt;
        }
}
int main(){
        int n,data;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        printf("Enter the values in the nodes:");
        for(int i=0;i<n;i++){
                scanf("%d",&data);
                createnode(data);
        }
        printf("List after revesing:\n");
        reverse();
        display();
}
```
## 11.Sorting of Linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
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
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void sorted(){
        struct node *i,*j;
        int temp;
        for(i=phead;i!=NULL;i=i->nxt){
                for(j=i->nxt;j!=NULL;j=j->nxt){
                        if(i->val>j->val){
                                temp=i->val;
                                i->val=j->val;
                                j->val=temp;
                        }
                }
        }
}
void display(){
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}

int main(){
        int n,data;
        printf("Enter the total number of nodes:");
        scanf("%d",&n);
        for(int i=0;i<n;i++){
                printf("Enter the node:");
                scanf("%d",&data);
                insertnode(data);
        }
        printf("Sorted Array:");
        sorted();
        display();
}
```
## 12.Merging and sorting of an array.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
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
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void sorted(){
        struct node *i,*j;
        int temp;
        for(i=phead;i!=NULL;i=i->nxt){
                for(j=i->nxt;j!=NULL;j=j->nxt){
                        if(i->val>j->val){
                                temp=i->val;
                                i->val=j->val;
                                j->val=temp;
                        }
                }
        }
}
void display(){
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
}

int main(){
        int n1,n2,data;
        printf("Enter the nodes in list1:\n");
        scanf("%d",&n1);
        for(int i=0;i<n1;i++){
                printf("Enter the node:");
                scanf("%d",&data);
                insertnode(data);
        }
        printf("Enter the nodes in list2:\n");
        scanf("%d",&n2);
        for(int i=0;i<n2;i++){
                printf("Enter the node:");
                scanf("%d",&data);
                insertnode(data);
        }
        printf("Sorted Array:");
        sorted();
        display();
}
```
## 13.Count the number of nodes in a linked list.
```c
#include<stdio.h>
#include<stdlib.h>
struct node{
        int val;
        struct node *nxt;
};
struct node *phead=NULL;
void insertnode(int d){
        struct node *pnew,*ptrav;
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL){
                printf("malloc error");
                return;
        }
        pnew->val=d;
        pnew->nxt=NULL;
        if(phead==NULL){
                phead=pnew;
                return;
        }
        else{
                ptrav=phead;
                while(ptrav->nxt!=NULL){
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void count(){
        struct node *ptrav;
        int count=0;
        ptrav=phead;
        while(ptrav!=NULL){
                ptrav=ptrav->nxt;
                count++;
        }
        printf("count of the nodes:%d\n",count);
}
void display(){
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL){
                printf("%d ",ptrav->val);
                ptrav=ptrav->nxt;
        }
        printf("\n");
}
int main(){
        insertnode(10);
        insertnode(20);
        insertnode(30);
        insertnode(40);
        insertnode(50);
        display();
        count();
        return 0;
}
```
