## 1. Write a program in C to count the total number of alphabets, digits and special characters in a String.
```c
#include<stdio.h>
#include<string.h>
void counting(char s[]){
        int alph=0,digits=0,symb=0;
        for(int i=0;s[i]!='\0';i++){
                if((s[i]>='a' && s[i]<='z')||(s[i]>='A' && s[i]<='Z'))
                        alph++;
                else if(s[i]>='0' && s[i]<='9')
                        digits++;
                else
                        symb++;
        }
        printf("No of Alphabets=%d\n",alph);
        printf("No of Digits=%d\n",digits);
        printf("No of Symbols=%d\n",symb);
}
int main(){
        char str[100];
        fgets(str,sizeof(str),stdin);
        if(str[strlen(str)-1]=='\n')
                str[strlen(str)-1]='\0';
        void (*ptr)(char [])=&counting;
        ptr(str);
}
```
