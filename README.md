# Black-and-White
Problem of day 9-dec-2022

```
def numOfWays(M, N):
    ans = 0
    total = M*N
    mod = pow(10,9) + 7
    dirt = [[2,1], [-2, 1], [-2, -1], [2, -1], [1, 2], [1, -2], [-1, 2], [-1, -2]]
    for i in range(M):
        for j in range(N):
            count = 0
            for x,y in dirt:
                if 0 <= i+x<M and 0<=y+j<N:
                    count += 1
            ans += (total - 1 - count)%mod
            ans = ans%mod
    return ans
