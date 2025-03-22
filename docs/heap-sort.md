---
author: haromeng
created: 2021-08-09 10:18
date: 2024/11/5
title: 堆排序
---


* **堆**：是一颗完全二叉树
* **小根堆**：父节点的值 <= 子节点的值
* **大根堆**：父节点的值 >= 子节点的值

对节点使用**左右孩子编号发**

![image.png](https://ylgg.oss-cn-wuhan-lr.aliyuncs.com/img/20241029211433.png)


1. 节点i的左孩子是2i
2. 节点i的右孩子是2i+1
3. 节点i的父节点是i/2

**堆**（完全二叉树）可以用**一维数组**存储

## 堆的插入

> [!note]把新元素从队尾插入，再逐层上浮到何时位置

![image.png](https://ylgg.oss-cn-wuhan-lr.aliyuncs.com/img/20241029212255.png)

![image.png](https://ylgg.oss-cn-wuhan-lr.aliyuncs.com/img/20241029212310.png)

```cpp
int a[N],cnt;

void up(int u)//上浮
{
	if(u/2 && a[u/2] > a[u])
		swap(a[u],a[u/2]),up(u/2);
}

void push(int x)
{
	a[++cnt] = x;
	up(cnt);
}

```

## 堆的删除

> [!note] 
> 把尾元素移动到根上，再逐层**下沉**到合适位置

例如：删除根元素

![image.png](https://ylgg.oss-cn-wuhan-lr.aliyuncs.com/img/20241029212821.png)

![image.png](https://ylgg.oss-cn-wuhan-lr.aliyuncs.com/img/20241029212833.png)

```cpp
void down(int u)
{
	int v = u;
	if(u * 2 <= cnt && a[u * 2] < a[v]) v = u * 2 ;
	if(u * 2 + 1 <= cnt && a[u * 2 + 1] < a[v]) v = u * 2 + 1;
	if (u != v) swap(a[u], a[v]), down(v);
}

void pop(){
	a[1] = a[cnt--];
	down(1);

}
```

