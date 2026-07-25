# Rearrange-negative-before-positive
#include<stdio.h>

void stableRearrange(int arr[], int n) {
    int temp[n];
    int k = 0;

    for (int i = 0; i < n; i++) {     
        if (arr[i] < 0) {
            temp[k++] = arr[i];
        }
    }

    
    for (int i = 0; i < n; i++) {       
        if (arr[i] >= 0) {
            temp[k++] = arr[i];
        }
    }

 
    for (int i = 0; i < n; i++) {       
        arr[i] = temp[i];
    }
}

int main() {
    int arr[] = {12, -7, 5, -3, -1, 8, 10, -2};
    int n = sizeof(arr) / sizeof(arr[0]);

    stableRearrange(arr, n);

    printf("Rearranged array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}
