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

## PROBELM: 04
### SHUFFLE AN ARRAY

```c
#include <stdio.h>
#include <stdlib.h>

int* suffle(int* nums, int numsSize, int n, int* returnSize){
    int* results = (int*) malloc(numsSize*sizeof(int));
    int k = 0;
    for(int i=0; i<n; i++){
        results[k] = nums[i];
        k++;
        results[k] = nums[i+n];
        k++;
    }
    return results;
}

int main(){
    int nums[] = {1, 2, 3, 4, 5, 6};
    int returnSize;
    int numsSize = sizeof(nums)/sizeof(nums[0]);

    int* results = suffle(nums, 6, 3, &returnSize);

    for(int i=0; i<numsSize; i++){
        printf("%d ", results[i]);
    }
    printf("\n");
    free(results);
    return 0;
}
```

## PROBLEM:03
### TRANSFORM AN ARRAY BY PARITY

```c
#include <stdio.h>
#include <stdlib.h>
int* transformArray(int* nums, int numsSize, int* returnSize){
    *returnSize = numsSize;
    int count=0;
    int* result = (int*) malloc(numsSize * sizeof(int));
    for(int i=0; i<numsSize; i++){
        if(nums[i] % 2 == 0){
            result[i] = 0;
            count++;
        }
        else{
            result[i] = 1;
        }
    }
//sorting
    int index=0;
    for(int i=0; i<count; i++){
        result[index] = 0;
        index++;
    }
    for(int i=count; i<numsSize; i++){
        result[index] = 1;
        index++;
    }
    return result;
}

int main(){
    int nums[] = {4, 3, 2, 1};
    int returnSize;
    int numsSize = sizeof(nums)/sizeof(nums[0]);

    int* result = transformArray(nums, 4, &returnSize);
    printf("Result is:");
    for(int i=0; i<numsSize; i++){
        printf("%d", result[i]);
    }
    printf("\n");

    free(result);

    return 0;
}
```   



