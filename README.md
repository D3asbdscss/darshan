 [2:22 pm, 15/07/2023] 🌄: Write a function that takes an array of integers and a rotation count as input and rotates the elements of the array to the right by the given rotation count.
[2:23 pm, 15/07/2023] darshan: public class ArrayRotation {
    public static void rotateArray(int[] arr, int rotationCount) {
        int n = arr.length;
        
        // Normalize the rotation count
        rotationCount = rotationCount % n;
        
        // Handle edge cases
        if (rotationCount == 0) {
            return;
        }
        
        // Reverse the entire array
        reverse(arr, 0, n - 1);
        
        // Reverse the first rotationCount elements
        reverse(arr, 0, rotationCount - 1);
        
        // Reverse the remaining elements
        reverse(arr, rotationCount, n - 1);
    }
    
    private static void reverse(int[] arr, int start, int end) {
        while (start < end) {
            int temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            
            start++;
            end--;
        }
    }
    
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        int rotationCount = 2;
        
        rotateArray(arr, rotationCount);
        
        // Print the rotated array
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
}
