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

### 3.17

今天又敲了一些數學題，感覺有些眼高手低了...甚至語法都沒有記清楚

### 3.19

俺枯了 dfs bfs也寫的磕磕絆絆
```
"".join(list); list(str) # 列表與字符串互轉
del list[now:] # 回溯刪除
from collections import deque; d=deque(); d.appendleft(); d.popleft(); # 雙端隊列
sorted(a, reverse = True, key = cmp) # sort參數
```

### 3.20

今天寫了一些搜索和并查集
```
def find(x, parent):
    if parent[x] != x: parent[x] = find(parent[x], parent)
    return parent[x]
def union(x, y, parent, rank):
    root_x = find(x, parent); root_y = find(y, parent)
    if root_x == root_y: return
    if rank[root_x] < rank[root_y]: parent[root_x] = root_y
    elif rank[root_x] > rank[root_y]: parent[root_y] = root_x
    else: parent[root_y] = root_x; rank[root_x] += 1
```
