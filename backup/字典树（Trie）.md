# 字典树（Trie）详解
## 字典树的概念
![a047c079f3f271668ec60fcf98c79ae](https://github.com/user-attachments/assets/85cf4d7e-a7b3-4706-8e3e-25a96cf70186)

将字符串以字典方式存储，建成一棵字典树，每个节点都是一个字母，是一种高效存储查询字符串的数据结构。
## 字典树的功能
功能超级广泛：
+ 维护字符串集合（字典）
+ 插入，查询，统计结点个数等操作
+ 字典序排序
+ 求集合内两个字符串的LCP（Longest Common Prefix，最长公共前缀）
+ 在字符串数量过大map被卡时可以用字典树来存，结点序号表示某个字符串
## 代码实现
直接贴上模板，很好理解。
```cpp
//对于字符串比较多的要统计个数的，map被卡的情况下，直接用字典树
//很多题都是要用到节点序号来表示某个字符串
const int maxn = 2e6 + 5;//如果是64MB可以开到2e6+5，尽量开大
int tree[maxn][30];//tree[i][j]表示节点i的第j个儿子的节点编号
bool flagg[maxn];//表示以该节点结尾是一个单词
int tot=0;//总节点数
void insert(string s){
    int  len = s.size();
    int root = 0;
    for (int i = 0; i < len; i++){
        int id = s[i] - '0';
        if (!tree[root][id]) tree[root][id] = ++tot;
        root = tree[root][id];
    }
    flagg[root] = true;
}
//查询操作，按具体要求改动,没有flagg判定
bool _find(string s){
    int len = s.size();
    int root = 0;
    for (int i = 0; i < len; i++){
        int id = s[i] - '0';
        if (!tree[root][id]) return false;
        root = tree[root][id];
    }
    return true;
}
void init()//最后清空，节省时间
{
    for (int i = 0; i <= tot; i++)
    {
        flagg[i] = false;
        for (int j = 0; j < 10; j++)
            tree[i][j] = 0;
    }
    tot = 0;//RE有可能是这里的问题
}
```
