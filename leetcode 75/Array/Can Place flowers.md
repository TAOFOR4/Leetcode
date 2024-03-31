```
bool canPlaceFlowers(int* flowerbed, int flowerbedSize, int n) {
    int count = 0; // To count plantable spots

    for(int i = 0; i < flowerbedSize; i++) {
        // Check if the current, previous, and next spots are empty
        if (flowerbed[i] == 0 &&
            (i == 0 || flowerbed[i - 1] == 0) &&
            (i == flowerbedSize - 1 || flowerbed[i + 1] == 0)) {
            flowerbed[i] = 1; // Plant a flower here
            count++;
        }
        if (count >= n) return true; // If we have planted enough flowers
    }

    return count >= n;
}
```