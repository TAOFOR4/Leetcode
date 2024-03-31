```
char* mergeAlternately(char* word1, char* word2) {
    int length_word1 = strlen(word1);
    int length_word2 = strlen(word2);
    int total_length = length_word1 + length_word2 + 1; // +1 for the null terminator

    char* word3 = (char*)malloc(total_length * sizeof(char)); // Allocate memory for char, not int

    int index = 0; // Index for the new string
    int i = 0; // Index for word1 and word2
    while (i < length_word1 || i < length_word2) {
        if (i < length_word1) {
            word3[index++] = word1[i];
        }
        if (i < length_word2) {
            word3[index++] = word2[i];
        }
        i++;
    }
    
    word3[index] = '\0'; // Add null terminator at the end

    return word3;
}
```