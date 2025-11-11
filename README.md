# LeetCode.submission01

## PROBLEM:01 
### RUNNING SUM OF 1-D ARRAY

```c
#include <stdio.h>

int* runningSum(int* nums, int numsSize, int* returnSize){
    *returnSize = numsSize;
    int sum=0;
    for(int i =0; i<numsSize; i++){
        sum+=nums[i];
        nums[i] = sum;
    }
    return nums;
}
int main(void){
    int nums[] = {1,2,3,4};
    int returnSize;
    int numsSize = sizeof(nums)/sizeof(nums[0]);

   int* result = runningSum(nums, numsSize, &returnSize);
   printf("the running sum of 1D array is:\n");
   for(int i=0; i<numsSize; i++){
        printf("%d ", result[i]);
   }
   printf("\n");

   return 0;
}
```



