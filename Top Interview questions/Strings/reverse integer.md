```

int reverse(int x) {

    long long sum = 0; // Use long long for intermediate calculations to handle overflow

    while (x != 0) {
        int digit = x % 10;
        x /= 10;

        // Use pow and check for overflow in the same step
        sum = sum * 10 + digit;

        // Check for overflow
        if (sum > INT_MAX || sum < INT_MIN) {
            return 0;
        }
    }

    return (int)sum;
}

```