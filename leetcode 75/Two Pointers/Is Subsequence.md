```
bool isSubsequence(char* s, char* t) {
    int s_length = strlen(s);
    int t_length = strlen(t);    
    int index=0;

   

    for(int i=0;i<t_length;i++)
    {
        if(s_length==index) return true;

        if(t[i]==s[index]) index++;
        
    }

    if(s_length==index) return true;

    return false;
}
```