# 树与二叉树
# 树的基本性质

<font face="楷体" color="black" size=5>
1. 树的节点数等于所有节点的度数之和加1 <br/>
2. 度为m的数中第i层上之多有m^i-1个结点 （i>=1）<br/>
3. 高度为h的m叉树之多有(m^h -1)/(m-1)个结点<br/>
4. 具有n个结点的m叉树的最小高度为logm n（n(m-1)+1） 向上取整<br/>
</font>



# 二叉树
> 

## 二叉树的遍历

### 先序遍历
```C++
void PreOrder(BiTree T){
    if(T!=NULL){
        visit(T);
        PreOrder(T->lchild);
        PreOrder(T->rchild);
    }
}
```
### 中序遍历

### 后序遍历


### 二叉树的层次遍历

### 深度优先

### 广度优先

### 线索二叉树

### 中序线索二叉树

### 先序

### 后序