```
void reverseString(char* s, int sSize) {
    int j=sSize-1;
    char temp;
    for(int i=0;i<j;i++)
    {
        temp=s[j];
        s[j]=s[i];
        s[i]=temp;
        j--;
    }
}
```