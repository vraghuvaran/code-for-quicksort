#include <stdio.h>
#include <stdlib.h>
void swap(int *a,int *b)
{
    int t;
    t=*a;
    *a=*b;
    *b=t;
}

void quicksort(int a,int l,int r)
{
    int c;
    if(l<r)
    {
    c=partition(a,l,r);
    quicksort(a,l,c-1);
    quicksort(a,c+1,r);
    }
}
int partition(int a[],int l,int r)
{
    int pivot=a[r];
    int i=l-1,j;
    for(j=l;j<r;j++)
    {
        if(a[j]<pivot)
        {
            i++;
            swap(&a[i],&a[j]);
        }
    }
    swap(&a[i+1],&a[r]);
    return i+1;
}
int main()
{
    int n,i,a[25];
     printf("enter the number of elements");
     scanf("%d",&n);
     printf("enter the elements");
     for(i=0;i<n;i++)
        scanf("%d",&a[i]);
     quicksort(a,0,n-1);
     for(i=0;i<n;i++)
        printf("%3d",a[i]);
}
