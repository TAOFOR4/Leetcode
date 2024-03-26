```
#include <limits.h>
#include <string.h>
#include <ctype.h> // For isdigit

int myAtoi(char* s) {
    int i = 0;
    long long sum = 0; // Use long long for intermediate calculations to prevent overflow
    int sign = 1; // Assume positive sign initially

    // Skip leading whitespaces
    while (s[i] == ' ') {
        i++;
    }

    // Check for sign
    if (s[i] == '-' || s[i] == '+') {
        sign = (s[i] == '-') ? -1 : 1;
        i++;
    }

    // Convert number
    while (isdigit(s[i])) {
        sum = sum * 10 + (s[i] - '0');
        i++;

        // Check for overflow and clamp the value within INT range
        if (sign == 1 && sum > INT_MAX) {
            return INT_MAX;
        } else if (sign == -1 && -sum < INT_MIN) {
            return INT_MIN;
        }
    }

    sum *= sign;

    return (int)sum;
}

```