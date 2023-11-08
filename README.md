# test_11_8
#include <stdio.h>

//平衡二叉树
typedef struct AVLNode{
	int key;
	int balance;
	struct AVLNode *lchild,*rchild;
}AVLNode,*AVLTree;

//红黑树
struct RBNode{
	int key;
	RBNode *parent;
	RBNode *lchild,*rchild;
	int color;
};

//B树(5叉查找树）
struct Node{
	int keys[4];
	struct Node *child[5];
	int num;
};

//直接插入排序
void InsertSort(int A[],int n){
	int i,j,temp;
	for(i=1;i<n;i++){
		if(A[i] < A[i-1])
			temp = A[i];
		for(j=i-1;j>=0 && A[j]>temp;--j)
			A[j+1] = A[j];
		A[j+1] = temp;
	}
}
//带哨兵
void InsertSort(int A[],int n){
	int i,j;
	for(i=2;i<=n;i++){
		if(A[i] < A[i-1])
			A[0] = A[i];
		for(j=i-1;A[0]<A[j];--j)
			A[j+1] = A[j];
		A[j+1] = A[0];
	}
}
