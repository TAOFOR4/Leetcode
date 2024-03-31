```
int maxArea(int* height, int heightSize) {
    int left = 0;
    int right = heightSize-1;

    int area = 0;
    int temp = 0;

    while(left<right)
    {
        if(height[left]<height[right])
        {
            temp = height[left]*(right-left);
            left++;
            if(temp>area)
            {
                area=temp;
            }
        } 
        else
        {
            temp = height[right]*(right-left);
            right--;
            if(temp>area)
            {
                area=temp;
            }
        }
    }

    return area;
}

```