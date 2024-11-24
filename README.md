# Complete-Collection-Check

Lily has a collection of n numbered tokens in an array called nums, and she wants to check if her collection is “complete.” For her collection to be complete, it must satisfy two rules:




It should contain each number from 1 up to n/2, and

Each of these numbers should appear exactly twice. Can you help Lily determine if her collection meets these requirements?


If it does, she’ll say “Yes,” and if it doesn’t, she’ll say “No.”

def is_collection_complete(n, nums):
    if n % 2 != 0:  # n must be even
        return "No"
    
    target_count = n // 2
    freq = {}
    
    # Count the frequency of each number in nums
    for num in nums:
        if num <= target_count:  # Only track numbers <= n/2
            freq[num] = freq.get(num, 0) + 1

    # Verify all numbers from 1 to n/2 have exactly 2 occurrences
    for i in range(1, target_count + 1):
        if freq.get(i, 0) != 2:
            return "No"

    return "Yes"

# Input
n = int(input().strip())
nums = list(map(int, input().strip().split()))

# Output
print(is_collection_complete(n, nums))
