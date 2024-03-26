```
void merge(int* nums1, int nums1Size, int m, int* nums2, int nums2Size, int n) {
    int i = m - 1; // Last element index of the initial segment of nums1
    int j = n - 1; // Last element index of nums2
    int k = m + n - 1; // Last element index of the merged array

    // Merge in reverse order
    while (j >= 0) {
        if (i >= 0 && nums1[i] > nums2[j]) {
            nums1[k] = nums1[i];
            i--;
        } else {
            nums1[k] = nums2[j];
            j--;
        }
        k--;
    }

    // No need to handle the case where elements from nums1 remain
    // because they are already in place. If j >= 0 loop exits, all remaining
    // elements in nums2 have been correctly placed into nums1.
}

```