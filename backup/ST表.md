动态规划思想，倍增，nlogn复杂度
```cpp
#include <bits/stdc++.h>
using namespace std;
#define MaxN 100002
int f[MaxN][22];
int __lg[100001] = { -1 };
int n, m;
inline int read() {
    int x = 0, f = 1;
    char ch = getchar();

    while (ch < '0' || ch > '9') {
        if (ch == '-')
            f = -1;

        ch = getchar();
    }

    while (ch >= '0' && ch <= '9') {
        x = x * 10 + ch - 48;
        ch = getchar();
    }

    return x * f;
}
void solve() {
    cin >> n >> m;

    for (int i = 1; i <= n; i++) {
        f[i][0] = read();
        __lg[i] = __lg[i / 2] + 1;
    }

    //f[j][i]表示从j开始到j+(1<<i)-1的区间

    //更新f数组
    for (int i = 1; i < 22; i++) {
        for (int j = 1; j + (1 << i) - 1 <= n; j++) {
            f[j][i] = max(f[j][i - 1], f[j + (1 << (i - 1))][i - 1]);
        }
    }

    //打印答案
    for (int i = 0; i < m; i++) {
        int l = read();
        int r = read();
        int s = __lg[r - l + 1];
        cout<< max(f[l][s], f[r - (1 << s) + 1][s])<<'\n';
    }

}
```