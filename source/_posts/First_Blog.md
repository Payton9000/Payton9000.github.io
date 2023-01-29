---
title: 显示测试
date: 2023-01-29 11:50:48
updated: 2023-01-29 11:50:48
type: "tags"
top_img: https://s1.ax1x.com/2023/01/29/pSac97d.jpg
copyright: false
description: "Go"
---
This is my first Blog.
```cpp
#include<bits/stdc++.h>
using namespace std;
const int N=100010;
int n,m;
int h[N],e[N],ne[N],idx;
int d[N];
void add(int a, int b)
{
    e[idx] = b, ne[idx] = h[a], h[a] = idx ++ ;
}
int bfs(){
    //memset(h, -1, sizeof h); //WA
    memset(d,-1,sizeof d); //AC
    queue<int> q;
    q.push(1);
    d[1]=0;
    // d[1] = 0;
    // q.push(1);
    while(q.size()){
        int t=q.front();
        q.pop();
        for(int i=h[t];i!=-1;i=ne[i]){
            int j=e[i];
            if(d[j]==-1){
                d[j]=d[t]+1;
                q.push(j);
            }
        }
    }
    return d[n];
}
int main(){
    scanf("%d%d", &n, &m);
    memset(h, -1, sizeof h);//AC
    //memset(d,-1,sizeof d);//TLE
    for (int i = 0; i < m; i ++ )
    {
        int a, b;
        scanf("%d%d", &a, &b);
        add(a, b);
    }

    cout << bfs() << endl;
    return 0;
}
```