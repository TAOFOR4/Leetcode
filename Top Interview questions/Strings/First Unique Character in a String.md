```
int firstUniqChar(char* s) {
    int hash[26]={0};
    int length = strlen(s);
    for(int i=0;i<length;i++)
    {
        hash[s[i]-'a']++;
    }
    for(int i=0;i<length;i++)
    {
        if(hash[s[i]-'a']==1)
        {
            return i;
        }
    }

    return -1;
}
```