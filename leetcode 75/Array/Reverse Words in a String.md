```

char* reverseWords(char* s) {
    int length = strlen(s);
    char storage[length/2 + 1][length + 1]; // Adjusted the size
    int wordCount = 0;

    // Parse the input string and fill the storage
    for (int i = 0; i < length; ) {
        while (s[i] == ' ' && i < length) i++; // Skip spaces
        if (i < length) {
            int k = 0;
            while (s[i] != ' ' && i < length) {
                storage[wordCount][k++] = s[i++];
            }
            storage[wordCount][k] = '\0'; // Correctly null-terminate the word
            wordCount++;
        }
    }

    // Allocate memory for the result
    char* result = (char*)malloc((length + 1) * sizeof(char));
    if (!result) return NULL; // Check for malloc failure

    int resIndex = 0;
    for (int j = wordCount - 1; j >= 0; j--) {
        int m = 0;
        while (storage[j][m] != '\0') {
            result[resIndex++] = storage[j][m++];
        }
        if (j > 0) { // Avoid trailing space
            result[resIndex++] = ' ';
        }
    }
    result[resIndex] = '\0'; // Null-terminate the result

    return result;
}
```