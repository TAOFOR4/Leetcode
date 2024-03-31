```
char* reverseVowels(char* s) {
    char* start = s;
    char* end = s + strlen(s) - 1;
    char temp;

    while(start<end)
    {
        if(*end=='a'||*end=='e'||*end=='i'||*end=='o'||*end=='u'||*end=='A'||*end=='E'||*end=='I'||*end=='O'||*end=='U')
        {
            while(*start!='a'&&*start!='e'&&*start!='i'&&*start!='o'&&*start!='u'&&*start!='A'&&*start!='E'&&*start!='I'&&*start!='O'&&*start!='U')
            {
                start++;
            }
            temp=*start;
            *start=*end;
            *end=temp;
            start++;
        }
        end--;
    }

    return s;
}
```