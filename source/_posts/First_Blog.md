---
title: Start
date: 2023-01-29 11:50:48
updated: 2023-01-29 11:50:48
type: "tags"
---
This is my first Blog.
```cpp
#include<bits/stdc++.h>
using namespace std;
const int N=100010;
int n,m;
int h[N],e[N],ne[N],idx;
int d[N];
vector<int> q;
void add(int a,intb){
    e[idx]=b;
    ne[idx]=h[a];
    h[a]=idx++;
}
int bfs(){
    memset(h,-1,sizeof(h));
    q.push(1);
    d[1]=0;
    while(!q.empty()){
        auto t=q.front();
        q.pop();
        for(int i=h[t];i!=-1;i=ne[i]){
            int j=e[i];
            if(d[j]==-1){
                d[j]=d[i]+1;
                q.push(j);
            }
        }
    }
    return d[n];
}
int main(){
    cin>>n>>m;
    memset(d,-1,sizeof(d));
    for(int i=0;i<m;i++){
        int a,b;
        cin>>a>>b;
        add(a,b);
    }
    cout<<bfs()<<endl;
    return 0;
}
```