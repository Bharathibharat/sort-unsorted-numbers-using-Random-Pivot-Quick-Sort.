# sort-unsorted-numbers-using-Random-Pivot-Quick-Sort.
import random

def partition(A, left_index, right_index):
    pivot = A[left_index]
    i = left_index + 1
    for j in range(left_index + 1, right_index):
        if A[j] < pivot:
            A[j], A[i] = A[i], A[j]
            i += 1
    A[left_index], A[i - 1] = A[i - 1], A[left_index]
    return i - 1

def quick_sort_random(A, left, right):
    if left < right:
        # Choose a random pivot and swap with leftmost element
        pivot = random.randint(left, right - 1)
        A[pivot], A[left] = A[left], A[pivot]
        pivot_index = partition(A, left, right)
        quick_sort_random(A, left, pivot_index)      # Left side
        quick_sort_random(A, pivot_index + 1, right) # Right side

# Test case 1
nums = [4, 3, 5, 1, 2]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort:")
print(nums)

# Test case 2
nums = [5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort:")
print(nums)

# Test case 3
nums = [1.1, 1, 0, -1, -1.1, 0.1]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort:")
print(nums)

# Test case 4: sorting subset
nums = [1.1, 1, 0, -1, -1.1, 0.1]
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 1, len(nums))
print("After applying Random Pivot Quick Sort from index 1:")
print(nums)

# Test case 5: characters
nums = ['z','a','y','b','x','c']
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 0, len(nums))
print("After applying Random Pivot Quick Sort:")
print(nums)

# Test case 6: characters, subset
nums = ['z','a','y','b','x','c']
print("\nOriginal list:")
print(nums)
quick_sort_random(nums, 2, len(nums))
print("After applying Random Pivot Quick Sort from index 2:")
print(nums)
