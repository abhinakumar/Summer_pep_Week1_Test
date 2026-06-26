# Summer_pep_Week1_Test

 ## Q1
 def rag(words, k):
    count = {}
    l1 = []
    for w in words.split():
        if w not in count:
            l1.append(w)
        count[w] = count.get(w, 0) + 1
    return [w for w in l1 if count[w] >= k]

text = input()
k = int(input())
print(rag(text, k))

## Q2
def min_trip(weight):
    weight.sort()
    l, r, trip = 0, len(weight) - 1, 0
    while l <= r:
        if weight[l] + weight[r] <= 3.0:
            l += 1
        r -= 1
        trip += 1
    return trip

weight = list(map(float, input().split(" ")))
print(min_trip(weight))

## Q3

def getMaxProfit(PandL, k):
    max_profit = float('-inf')
    for size in range(1, k + 1):
        curr = sum(PandL[:size])
        max_profit = max(max_profit, curr)
        for i in range(size, len(PandL)):
            curr += PandL[i] - PandL[i - size]
            max_profit = max(max_profit, curr)
    return max_profit

n = int(input("n= "))
PandL = [int(input()) for _ in range(n)]
k = int(input("k= "))
print(f"Max profit is {getMaxProfit(PandL, k)}")
