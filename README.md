# Stack-2-DS
Practice program
def twoStacks(maxSum, a, b):
    s = 0
    count = 0
    i = 0
    j = 0

    # Take elements from stack a
    while i < len(a) and s + a[i] <= maxSum:
        s += a[i]
        i += 1

    count = i

    # Now try elements from stack b
    while j < len(b) and i >= 0:
        s += b[j]
        j += 1

        while s > maxSum and i > 0:
            i -= 1
            s -= a[i]

        if s <= maxSum:
            count = max(count, i + j)
        j += 0

    return count


# Example
a = [4, 2, 4, 6, 1]
b = [2, 1, 8, 5]
maxSum = 10

result = twoStacks(maxSum, a, b)
print("Maximum score:", result)

sample input:
Stack A = [4, 2, 4, 6, 1]
Stack B = [2, 1, 8, 5]
maxSum = 10

sample output:
Maximum score: 4
