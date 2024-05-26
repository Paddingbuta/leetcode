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

### 3.21

聽了cs231n的機器學習 被死去的高數瘋狂衝擊

### 3.22

今天看了ml的一些經典算法，還碼了區間dp樹形dp狀壓dp的板子題
```
fma[i][j]=max(fma[i][j-1],fma[i+1][j])+sum[j]-sum[i-1]
dp[i][j]=max(dp[i][j],dp[v][j-1]+val[v])(v=sons of i)
```

### 3.23

各種dp 貪心 爆搜之類的隨便寫了一點

### 3.24

發燒咗 一整日都喺瞓覺🤒

### 3.28

仲未退燒🚬 看了一些簡單的圖論

### 4.9

好耐冇做題 揾咗啲模擬貪心寫

### 4.12

```
num=[int(x) for x in input().split()]
s.append(list(map(int,input().split())))
def __lt__(self,other)
```
### 5.15

大模擬 暈酡酡

### 5.25

```
diff[x1][y1] += c, diff[x2+1][y2+1] += c;
diff[x2+1][y1] -= c, diff[x1][y2+1] -= c; //差分

priority_queue<int, vector<int>, greater<int> >q; //優先隊列


vector<pair<int, map<string, int>>> vecMap;
map<string, int> map1 = {{"apple", 5}, {"banana", 3}};
vecMap.push_back(make_pair(1, map1));
for (const auto& pair : vecMap) pair.first pair.second //每個元素都是一個pair的vector 用来存储多个 map

f[t][j] = f[t][j] + f[1-t][j-k]; //滾動數組
```

### 5.26

二個大int數相乘后取模會溢出 需開long long
