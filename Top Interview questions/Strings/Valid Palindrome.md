```
bool isPalindrome(char* s) {
   int j=0;
   for(int i=0;i<strlen(s);i++)
   {
    if (isalnum(s[i]))
    {
        s[j]=s[i];
        j++;
    }
   }

   for(int i=0;i<j/2;i++)
   {
    if(tolower(s[i]) != tolower(s[j-i-1]))
    {return false;}
   }

   return true;

}
```