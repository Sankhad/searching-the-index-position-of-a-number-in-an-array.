# searching-the-index-position-of-a-number-in-an-array.
You are given an integer array 'A' of size 'N', sorted in non-decreasing order. You are also given an integer 'target'.    Your task is to write a function to search for 'target' in the array 'A'. If it exists, return its index in 0-based indexing. If 'target' is not present in the array 'A', return -1.  in java(17)

import javai.io.*;
public class BinarySearch {
    public static int search(int[] A, int target) {
        int left = 0;
        int right = A.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            // If the target is found at mid
            if (A[mid] == target) {
                return mid;
            }
            // If the target is greater, ignore left half
            else if (A[mid] < target) {
                left = mid + 1;
            }
            // If the target is smaller, ignore right half
            else {
                right = mid - 1;
            }
        }

        // If the target is not present in the array
        return -1;
    }

    public static void main(String[] args) {
        int[] A = {1, 3, 5, 7, 9, 11, 13};
        int target = 7;
        int index = search(A, target);
        if (index != -1) {
            System.out.println("Element found at index: " + index);
        } else {
            System.out.println("Element not found in the array.");
        }
    }
}
