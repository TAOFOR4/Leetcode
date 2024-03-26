```
char* longestCommonPrefix(char** strs, int strsSize) {
    if (strsSize == 0) {
        return strdup(""); // Return an empty string if there are no strings
    }
    char* common = (char*)malloc(strlen(strs[0]) + 1);
    if (common == NULL) {
        return NULL; // Memory allocation failed
    }
    int index = 0;
    while (strs[0][index] != '\0') {
        char currentChar = strs[0][index];
        for (int i = 1; i < strsSize; i++) {
            if (strs[i][index] != currentChar) {
                common[index] = '\0'; // Terminate the common prefix
                return common;
            }
        }
        common[index] = currentChar; // Copy the character into the common prefix
        index++;
    }
    common[index] = '\0'; // Ensure the result is null-terminated
    return common;
}
```