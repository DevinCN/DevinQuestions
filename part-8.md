# 概述
---
##### 排序有内部排序和外部排序，内部排序是数据记录在内存中进行排序，而外部排序是因排序的数据很大，一次不能容纳全部的排序记录，在排序过程中需要访问外存。
##### 我们这里说说八大排序就是内部排序。

![](/assets/1.gai_shu.jpg)

当n较大，则应采用时间复杂度为O(nlog2n)的排序方法：快速排序、堆排序或归并排序序。
快速排序：是目前基于比较的内部排序中被认为是最好的方法，当待排序的关键字是随机分布时，快速排序的平均时间最短；

## 1.插入排序—直接插入排序(Straight Insertion Sort)

### 基本思想:
将一个记录插入到已排序好的有序表中，从而得到一个新，记录数增1的有序表。即：先将序列的第1个记录看成是一个有序的子序列，然后从第2个记录逐个进行插入，直至整个序列有序为止。
要点：设立哨兵，作为临时存储和判断数组边界之用。
直接插入排序示例：

![](/assets/1.jpg)

如果碰见一个和插入元素相等的，那么插入元素把想插入的元素放在相等元素的后面。所以，相等元素的前后顺序没有改变，从原无序序列出去的顺序就是排好序后的顺序，所以插入排序是稳定的。

### 算法的实现：

package com;  
  
public class InsertSort {  
  
    public static void main(String[] args) {  
        int a[] = {3,1,5,7,2,4,9,6,10,8};    
        InsertSort  obj=new InsertSort();  
        System.out.println("初始值：");  
        obj.print(a);  
        obj.insertSort(a);  
        System.out.println("\n排序后：");  
        obj.print(a);  
  
    }  
  
    public void print(int a[]){  
        for(int i=0;i<a.length;i++){  
            System.out.print(a[i]+" ");  
        }  
    }  
    public void insertSort(int[] a) {  
        for(int i=1;i<a.length;i++){//从头部第一个当做已经排好序的，把后面的一个一个的插到已经排好的列表中去。  
            if(a[i]<a[i-1]){  
                int j;  
                int x=a[i];//x为待插入元素  
                a[i]=a[i-1];  
                for(j=i-1;  j>=0 && x<a[j];j--){//通过循环，逐个后移一位找到要插入的位置。  
                    a[j+1]=a[j];  
                }  ``
                a[j+1]=x;//插入  
            }  
                  
        }  
          
    }  
}


