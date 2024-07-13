#hackerrank challenge 1
def unboundedKnapsack(k, arr):
    dp = [0] * (k + 1)
    for i in range(1, k + 1):
        max_val = 0
        for num in arr:
            if num <= i:
                max_val = max(max_val, dp[i - num] + num)
        dp[i] = max_val
    return dp[k]

t = int(input())
for _ in range(t):
    n, k = map(int, input().split())
    arr = list(map(int, input().split()))
    print(unboundedKnapsack(k, arr))

