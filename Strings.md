## 1. Write a program in C to input a string and print it.
```c
#include<stdio.h>
int main(){

      char str[100];
      fgets(str,sizeof(str),stdin);
      printf("%s",str);
}
```
## 2. Write a program in C to find the length of a string without using library functions.
```c
#include<stdio.h>
int main(){
        char s1[30];
        scanf("%s",s1);
        printf("string=%d",s1);
        int i=0;
        while(i!='\0'){
                count++;
                i++;
        }
        printf("length of the string:%d",count);
}
```
## 3. Write a program in C to separate individual characters from a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char s1[100];
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        printf("Input string:%s\n",s1);
        printf("Individual characters in the string are:\n");
        for(int i=0;s1[i]!='\0';i++){
                printf("%c\n",s1[i]);
        }
}
```
## 4. Write a program in C to print individual characters of a string in reverse order.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char name[30];
        int len,temp;
        fgets(name,sizeof(name),stdin);
        if(name[strlen(name)-1]=='\n')
                name[strlen(name)-1]='\0';
        printf("string before reversing :%s\n",name);
        len=strlen(name);
        printf("string after reversing:\n");
        for(int i=len-1;i>=0;i--){
                printf("%c\n",name[i]);
        }
}
```
## 5. Write a program in C to count the total number of words in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){ 
    char str[1000];
    int count=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
    str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        if((i==0 && str[i]!=' ' && str[i]!=','&& str[i]!='\t')||((str[i]==' '||str[i]=='.'||
    str[i]=='\t'||str[i]==',')&&((str[i+1]!=' '&&str[i+1]!=','&&str[i+1]!='\t'&&str[i+1]!='.')))){
            count++;
        }
    }
    printf("count=%d",count);
}
```
## 6. Remove the newline character added by fgets() using strcspn().
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        printf("%s",str);
}
```
## 7.Write a C Program to check if a two strings are Anagram or not.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void sort(char str[]){
        for(int i=0;str[i]!='\0';i++){
                for(int j=i+1;str[j]!='\0';j++){
                        if(str[i]>str[j]){
                        char temp=str[i];
                        str[i]=str[j];
                        str[j]=temp;
                }
                }
        }
}
int main(){
        char str1[100],str2[100];
        int count=0;
        fgets(str1,sizeof(str1),stdin);
        if(str1[strlen(str1)-1]=='\n')
                str1[strlen(str1)-1]='\0';
        fgets(str2,sizeof(str2),stdin);
        if(str2[strlen(str2)-1]=='\n')
                str2[strlen(str2)-1]='\0';

        if(strlen(str1)!=strlen(str2)){
                printf("string is not a anagram");
                return 0;
        }
        for(int i=0;str1[i]!='\0';i++){
                str1[i]=tolower(str1[i]);
        }
        for(int i=0;str2[i]!='\0';i++){
                str2[i]=tolower(str2[i]);
        }
        sort(str1);
        sort(str2);
        if(strcmp(str1,str2)==0)
                printf("String is a anagram");
        else
                printf("string is not a anagram");

}
```
## 8.Write a C program to check if string is pangram or not.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void pangram(char str[]){
        for(char ch='a';ch<='z';ch++){
                int found=0;
                for(int i=0;str[i]!='\0';i++){
                        if(ch==str[i]){
                              found=1;
                              break;
                        }
                }
                if(found==0){
                        printf("Not a Pangram");
                        return ;
                }
        }
        printf("Pangram");
}
int main(){
        char s1[1000];
        fgets(s1,sizeof(s1),stdin);
        if(s1[strlen(s1)-1]=='\n')
                s1[strlen(s1)-1]='\0';
        for(int i=0;s1[i]!='\0';i++){
                s1[i]=tolower(s1[i]);
        }
        pangram(s1);
}
```
## 9. Write a program to reverse a string using recursion.
```c
#include<stdio.h>
#include<string.h>
void reverse(char str[],int start,int end){
        if(start>=end)
                return;
        char temp;
        temp=str[start];
        str[start]=str[end];
        str[end]=temp;
        reverse(str,start+1,end-1);
}
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int length=strlen(str);
        reverse(str,0,length-1);
        printf("\n%s",str);
}
```
## 10.Write a C program to print sum of numbers in a string.
```c
#include<stdio.h>
int main(){
        char str[]="Hello123bg43";
        int sum=0;
        for(int i=0;str[i]!='\0';i++){
                if(str[i]>='0'&&str[i]<='9'){
                        sum=sum+str[i]-'0';
                }
        }
        printf("Sum of the digits=%d",sum);
}
```
## 11.Write a C program to count number of vowels in a string.
```c
#include<stdio.h>
int main(){
        char str[100];
        int count=0;
        fgets(str,sizeof(str),stdin);
        for(int i=0;str[i]!='\0';i++){
                if(str[i]=='a' || str[i]=='e' || str[i]=='i' || str[i]=='o' || str[i]=='u'){
                        count++;
                }
        }
        printf("Number of vowels in a string=%d",count);
}
```
## 12.Write a C program to find substring in a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000],Aword[100];
    int found=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
       str[strlen(str)-1]='\0';
    fgets(Aword,sizeof(Aword),stdin);
    if(Aword[strlen(Aword)-1]=='\n')
       Aword[strlen(Aword)-1]='\0';
    int len1=strlen(str);
    int len2=strlen(Aword);
    for(int i=0;i<=len1-len2;i++){
        int j;
        for(j=0;j<len2;j++){
            if(str[i+j]!=Aword[j])
                break;
        }
        if(j==len2){
                found=1;
                break;
        }
    }
    if(found)
        printf("substring is found");
    else
        printf("substring is not found");
    
}
```
## 13.Write a function to reverse a string.
```c
#include<stdio.h>
#include<string.h>
char* reverse(char str1[]){
    int len=strlen(str1);
    for(int i=0,j=len;i<j;i++,j--){
        int temp=str1[i];
        str1[i]=str1[j];
        str1[j]=temp;
    }
    return str1;
}
int main(){
    char str[100];
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
       str[strlen(str)-1]='\0';
    reverse(str);
    printf("%s",str);
}
```
## 14. Write a program in C to find the maximum number of characters in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[100];
    int count=0;
    int len,freq;
    char maxcharacter;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    len=strlen(str);
    int fre[len];
    for(int i=0;i<len;i++){
        fre[i]=-1;
    }
    for(int i=0;i<len;i++){
        if(fre[i]==-1){
            count=0;
            for(int j=0;j<len;j++){
                if(str[i]==str[j]){
                    fre[j]=0;
                    count++;
                }
            }
            fre[i]=count;
        }
    }
    freq=fre[0];
    maxcharacter=str[0];
    for(int i=0;i<len;i++){
        if(fre[i]>freq){
            freq=fre[i];
            maxcharacter=str[i];
        }
    }
    printf("character %c repeates %d times",maxcharacter,freq);
}
```
## 15.Write a program in C to extract a substring from a given string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str1[1000],word[100];
    int k=0,a,len;
    fgets(str1,sizeof(str1),stdin);
    if(str1[strlen(str1)-1]=='\n')
        str1[strlen(str1)-1]='\0';
    printf("Enter the position the starting position(1-based index):");
    scanf("%d",&a);
    printf("Enter the length of the string:");
    scanf("%d",&len);
    for(int i=a-1;i<a-1+len&&str1[i]!='\0';i++){
        word[k++]=str1[i];
    }
    word[k]='\0';
    printf("%s",word);
}
```
## 16.Write a program in C to find the number of times a given word 'the' appears in the given string.
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main(){
    char str[1000],word[100];
    int count=0,k=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        str[i]=tolower(str[i]);
    }
    for(int i=0; ;i++){
        if(str[i]!=' '&&str[i]!='\0')
           word[k++]=str[i];
        else{
        word[k]='\0';
        if(strcmp(word,"the")==0)
            count++;
        k=0;
        }
        if(str[i]=='\0')
          break;
    }
    printf("the repeats %d times",count);
}
```
## 17.Write a program in C to read a sentence and replace lowercase characters with uppercase and vice versa.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000];
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        if(str[i]>='a'&&str[i]<='z')
            str[i]=str[i]-32;
        else if(str[i]>='A'&&str[i]<='Z')
            str[i]=str[i]+32;
    }
    printf("%s",str);
    
}
```
## 18.Write a program in C to remove characters from a string except alphabets.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000],word[100];
    int k=0;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0;str[i]!='\0';i++){
        if((str[i]>='a'&&str[i]<='z')||(str[i]>='A'&&str[i]<='Z'))
             word[k++]=str[i];
    }
    word[k]='\0';
    printf("%s",word);
}
```
## 19.Write a program in C to find the largest and smallest words in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str[1000],word[100],largest[100],smallest[100];
    int k=0,maxlen=0,minlen=1000;
    fgets(str,sizeof(str),stdin);
    if(str[strlen(str)-1]=='\n')
        str[strlen(str)-1]='\0';
    for(int i=0; ;i++){
        if((str[i]!=' '&&str[i]!='\0'))
             word[k++]=str[i];
        else{     
           word[k]='\0';
           if(strlen(word)>maxlen){
              maxlen=strlen(word);
              strcpy(largest,word);
           }
           if(strlen(word)<minlen&&strlen(word)>0){
               minlen=strlen(word);
               strcpy(smallest,word);
           }
           k=0;
        }
        if(str[i]=='\0')
              break;
    }
    printf("Largest string=%s\n",largest);
    printf("Smallest string=%s\n",smallest);
}
```
## 20.Write a program in C to combine two strings manually.
```c
#include<stdio.h>
#include<string.h>
int main(){
    char str1[1000],str2[1000];
    int len1,len2,k=0;
    printf("Enter the 1st string:");
    fgets(str1,sizeof(str1),stdin);
    if(str1[strlen(str1)-1]=='\n')
        str1[strlen(str1)-1]='\0';
    printf("\n");
    printf("Enter the 2nd string:");
    fgets(str2,sizeof(str2),stdin);
    if(str2[strlen(str2)-1]=='\n')
        str2[strlen(str2)-1]='\0';
    len1=strlen(str1);
    len2=strlen(str2);
    char string[len1+len2];
    for(int i=0;str1[i]!='\0';i++){
        string[k++]=str1[i];
    }
    for(int i=0;str2[i]!='\0';i++){
        string[k++]=str2[i];
    }
    string[k]='\0';
    printf("%s",string);
  
}
```
## 21.Write a C program to reverse each word in a sentence while keeping spaces, commas, and full stop in their original positions.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[1000],word[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len1=strlen(str);
        int k=0,len2;
        for(int i=0; ;i++){
                if(str[i]!=' '&&str[i]!=','&&str[i]!='.'&&str[i]!='\0')
                        word[k++]=str[i];
                else{
                    word[k]='\0';
                    for(int i=0,j=k-1;i<j;i++,j--){
                        int temp=word[i];
                        word[i]=word[j];
                        word[j]=temp;
                    }
                    printf("%s",word);
                    if(str[i]!='\0')
                            printf("%c",str[i]);
                    k=0;
                   }
                if(str[i]=='\0')
                        break;
        }
}
```
## 22. Write a C program to read a sentence and split it into words using spaces. Do not use strtok. Use pointer manipulation.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],word[100];
        int k=0;
        char *ptr;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(ptr=str; ;ptr++){
                if(*ptr!=' ' && *ptr!='.' && *ptr!=',' && *ptr!='\0')
                        word[k++]=*ptr;
                else{
                    word[k]='\0';
                    if(k>0)
                         printf("%s\n",word);
                    k=0;
                }
                if(*ptr=='\0')
                        break;
        }
}
```
## 23.Write a C program to read a sentence and split it into words using spaces. Do not use strtok. Use pointer manipulation.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100],word[100];
        int k=0;
        char *ptr;
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(ptr=str; ;ptr++){
                if(*ptr!=' ' && *ptr!='.' && *ptr!=',' && *ptr!='\0')
                        word[k++]=*ptr;
                else{
                    word[k]='\0';
                    if(k>0)
                         printf("%s\n",word);
                    k=0;
                }
                if(*ptr=='\0')
                        break;
        }
}
```
## 24.Replace vowels with nxt character in a string.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[100];
        printf("Enter the string:");
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        for(int i=0;str[i]!='\0';i++){
                if(str[i]=='a'||str[i]=='e'||str[i]=='i'||str[i]=='o'||str[i]=='u'||str[i]=='A'||str[i]=='I'||str[i]=='O'||str[i]=='U'||str[i]=='E')
                        str[i]=str[i]+1;
        }
        printf("%s",str);
}
```
## 25.Find the length of the last word.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char str[1000],word[100];
        int k=0;
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        int len=strlen(str),i;
        for(i=len-1;i>=0&&str[i]==' ';i--);
        for(;i>=0&&str[i]!=' ';i--){
                        word[k++]=str[i];
        }
        word[k]='\0';
        printf("%d",strlen(word));
}
```
## 26.Write a C program to read an integer target, an array of n integers, and print all indices where the array element equals target.
```c
#include<stdio.h>
int main(){
        int arr[]={1,3,4,6,5,67,9};
        int num,len;
        len=sizeof(arr)/sizeof(arr[0]);
        printf("Enter the number:");
        scanf("%d",&num);
        for(int i=0;i<len;i++){
                if(arr[i]==num){
                        printf("Index value=%d",i);
                }
        }
}
```
## 27.Write a C program to find and print all adjacent pairs in an array whose sum is equal to a given number k.
```c
#include<stdio.h>
int main(){
        int arr[]={1,2,3,4,5};
        int sum=0,k=3;
        for(int i=0;i<4;i++){
                sum=arr[i]+arr[i+1];
                if(sum==3){
                        printf("%d %d",arr[i],arr[i+1]);
                }
        }
}
```
## 28.Write a C program to check whether a given number is a Happy Number or not.
```c
#include<stdio.h>
int main(){
        int num,rem;
        printf("Enter the number:");
        scanf("%d",&num);
        while(num>9){
                int sum=0;
                while(num>0){
                        rem=num%10;
                        sum=sum+rem*rem;
                        num=num/10;
                }
                num=sum;
        }
        if(num==1)
                printf("Happy");
        else
                printf("Not Happy");
}
```
## 29.Write a C program to check whether the parentheses in a given expression are balanced or not.
```c
#include<stdio.h>
#include<string.h>
int main(){
        char exps[100];
        int top=-1;
        printf("Enter the expression:");
        fgets(exps,sizeof(exps),stdin);
        if(exps[strlen(exps)-1]=='\n')
                exps[strlen(exps)-1]='\0';
        for(int i=0;exps[i]!='\0';i++){
                if(exps[i]=='('){
                        top++;
                }
                else if(exps[i]==')'){
                        if(top==-1){
                                printf("Not Balanced");
                                return 0;
                        }
                        else
                                top--;
                }
        }
        if(top==-1)
                printf("Balanced");
        else
                printf("Not balanced");
}
```

