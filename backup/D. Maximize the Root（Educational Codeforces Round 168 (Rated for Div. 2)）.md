题目链接：https://codeforces.com/problemset/problem/1997/D
这道题刚开始想从叶子节点开始向根方向搜索，很难写，状态不好存，遂看了几篇题解，选择了树形dp的做法。
参考：https://www.cnblogs.com/zsc985246/p/18333684
用链式前向星存下这棵树，从根节点开始深搜，这样保证在访问父节点时他的子节点全部访问过了。用一个数组u存下访问每个节点时他的所有子节点中的最小值mn是多少，在搜到叶子节点时将u赋值为它自己的值；中间节点时若v>mn,将u赋值为mn，若v<mn,将u赋值为(v+mn)/2；到根节点可以简单粗暴直接加上mn作为答案。
```cpp
#include <bits/stdc++.h>
using namespace std;
int v[200005];
int u[200005];
int n;
//链式前向星
const int MAXN = 2e5 + 7;
int head[MAXN];
int cnt = 1;
struct edge {
    int to, nxt;
};
edge a[MAXN];
void add_edge(int u, int v) {
    //a[cnt].w = w;
    a[cnt].to = v;
    a[cnt].nxt = head[u];
    head[u] = cnt++;
}

void dfs(int x){
    ll mn = 1e9+7;
    for (int j = head[x]; j; j = a[j].nxt) {
        dfs(a[j].to);
        mn = min(mn, (ll)u[a[j].to]);
    }
    if (mn == 1e9+7) {
        u[x] = v[x];
        return;
    }
    if (x == 1) {
        v[x] += mn;
        return;
    }
    if (v[x] < mn) {
        u[x] = (v[x] + mn) / 2;
    }
    else {
        u[x] = mn;
    }
}

void init() {
    for (int i = 0; i <= n; i++) {
        head[i] = 0;
        v[i] = 0;
        u[i] = 0;
        cnt = 1;
        a[i].nxt = 0;
        a[i].to = 0;
    }
}

void solve() {  
    cin >> n;
    for (int i = 1; i <= n; i++) {
        cin >> v[i];
    }
    int x;
    for (int i = 2; i <= n; i++) {
        cin >> x;
        add_edge(x, i);
    }

    dfs(1);
    cout << v[1] << '\n';

    //cnt = 1;
    init();

}

signed main() {
    ios::sync_with_stdio(false);
    cin.tie(0);
    cout.tie(0);
    int t = 1;
    cin >> t;
    while (t--) solve();

    return 0;
}
```