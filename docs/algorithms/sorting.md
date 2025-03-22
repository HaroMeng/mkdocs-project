# 归并排序

## 算法思想

将一个需要排序的数不断地从中间分开,分成两个数组. 之后对两个数组进行比较, 将其合并为一个数组.

1. 找到分界点`(l + r) / 2`
2. 递归排序 left和right
3. 归并,合二为一
## 实现代码

```cpp
void merge_sort(int q[], int l, int r)
{
    if (l >= r) return;

    int mid = l + r >> 1;
    merge_sort(q, l, mid);
    merge_sort(q, mid + 1, r);

    int k = 0, i = l, j = mid + 1;
    while (i <= mid && j <= r)
        if (q[i] <= q[j]) tmp[k ++ ] = q[i ++ ];
        else tmp[k ++ ] = q[j ++ ];

    while (i <= mid) tmp[k ++ ] = q[i ++ ];
    while (j <= r) tmp[k ++ ] = q[j ++ ];

    for (i = l, j = 0; i <= r; i ++, j ++ ) q[i] = tmp[j];
}

```


# 快速排序

## 算法思想

快速排序是分治的思想，步骤：

1. 确定分界点，是随机选取的，也可以是q\[l]，q\[(l/r)/2],q\[r]，主意规定的有可能会导致时间复杂度变为 $O(n)$
2. 调整范围，确定分界点以后左边的数小于分界点，右边的数大于分界点
3. 归并处理左右两端

优化算法，分别取两端`i`和`j`，`i`和`j`分别向中间靠拢，当出现`i`与`j`，比较不符时，更换对应下标的值

## 算法实现

```cpp
void quick_sort(int q[], int l, int r)
{
    if (l >= r)
        return;
    int x = q[rand() % (r - l + 1) + l], i = l - 1, j = r + 1;//防止越界
    while (i < j)
    {
        do
            i++;
        while (q[i] < x);
        do
            j--;
        while (q[j] > x);
        if(i < j) swap(q[i],q[j]);
    }
    quick_sort(q, l, i - 1);
    quick_sort(q, i, r);
}

```

