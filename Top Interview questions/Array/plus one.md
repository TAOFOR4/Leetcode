```
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* plusOne(int* digits, int digitsSize, int* returnSize) {
    int incre = 1;


    for(int i=digitsSize-1; i>=0&&incre; i--)
    {
       
            if(digits[i]==9)
            {
                digits[i]=0;
                incre = 1;
            }
            else
            {
                digits[i]++;
                incre = 0;
            }
    

    }

    int *result;

    if (incre) {
        // If there's still a carry, we need an extra digit
        *returnSize = digitsSize + 1;
        result = (int*)malloc(*returnSize * sizeof(int));
        result[0] = incre; // The carry becomes the most significant digit
        // Copy the rest of the digits
        for (int i = 1; i < *returnSize; ++i) {
            result[i] = digits[i-1];
        }
    } else {
        // No extra digit needed
        *returnSize = digitsSize;
        result = (int*)malloc(*returnSize * sizeof(int));
        // Copy the digits
        for (int i = 0; i < digitsSize; ++i) {
            result[i] = digits[i];
        }
    }

    return result;

   
    
}
```