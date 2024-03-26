```
int strStr(char* haystack, char* needle) {
    int lengthh = strlen(haystack);
    int lengthn = strlen(needle);
    int check=0;
    for(int i=0;i<lengthh-lengthn+1;i++)
    {
        if(haystack[i]==needle[0])
        {
            check = 0;
            for(int j=0;j<lengthn;j++)
            {
                if(haystack[i+j]!=needle[j])
                {
                    check = -1;
                    break;
                }
            }
            if(check==0)
            {
                return i;
            }
        }
    }

    return -1;
}
```