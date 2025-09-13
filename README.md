# leetcode26
Approach: Two-Pointer Technique
This solution uses the two-pointer technique to efficiently remove duplicates in-place while maintaining the sorted order.

Intuition:
Since the array is already sorted, all duplicate elements will be adjacent to each other. We can use:
A slow pointer (uniqueIndex) that tracks the position where the next unique element should be placed
A fast pointer (i) that iterates through the array to find new unique elements

Algorithm:
Initialization: Start with uniqueIndex = 0 (the first element is always unique)
Iteration: Traverse the array from the second element (i = 1) to the end

Comparison: For each element nums[i]:
If it's different from the last unique element (nums[uniqueIndex]), it's a new unique element
Increment uniqueIndex and copy nums[i] to nums[uniqueIndex]
Result: The number of unique elements is uniqueIndex + 1

Complexity Analysis
Time Complexity: O(n) - Single pass through the array
Space Complexity: O(1) - Only uses constant extra space (two pointers)

Alternative Approaches
Using STL (C++): nums.erase(unique(nums.begin(), nums.end()), nums.end());
Returns iterator to new end, then erase remaining elements
Less efficient for the problem constraints (modifies array size)

Hash Set Approach:
Would require O(n) extra space
Doesn't maintain order (unless using LinkedHashSet)
Not optimal for this problem

Conclusion
The two-pointer technique provides the most efficient solution for this problem, achieving optimal time and space complexity while maintaining the original order of elements. This pattern is widely applicable to other array manipulation problems involving sorted data.
