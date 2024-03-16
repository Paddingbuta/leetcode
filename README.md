# leetcode
- 記錄一隻算法能力很平庸的鼠鼠的刷題日常
### 3.16

今天看了一些思路清奇還很有意思的數學題，遇到這類題還是要先沉住氣打暴力or公式推導再發現其中的規律；還學習了質數篩和分解質因數算法，附上關鍵部分代碼
```
# 一個素數的倍數都不是素數
n,ans = 1000,[]
flag = [0 for _ in range(n+1)]
for i in range(2,n+1):
    if(not flag[i]): ans.append(i)
    for j in range(len(ans)):
        if(ans[j]*i>n): break
        flag[ans[j]*i] = 1
        if(i%ans[j]==0): break
```
