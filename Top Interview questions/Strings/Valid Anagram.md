```

bool isAnagram(char* s, char* t) {
    int hash[26] = {0};
    int lengths = strlen(s);
    int lengtht = strlen(t);
    for(int i=0; i<lengths;i++)
    {
        hash[s[i]-'a']++;
    }
    for(int i=0; i<lengtht;i++)
    {
        hash[t[i]-'a']--;
    }
    for(int i=0;i<26;i++)
    {
        if(hash[i]!=0)
        {
            return false;
        }
    }
    return true;
}
```