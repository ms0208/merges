# merges
# include<stdio.h>

void merge(int a[],int lb,int mid,int ub)
{
    int i,j,k,b[10];
    i = lb;
    j = mid + 1;
    k = lb ; 
    while(i<=mid && j<=ub)
    {
        if(a[i]<=a[j])
        {
            b[k++] = a[i++];
           
        }
        else
        {
            b[k++] = a[j++];
           
          
        }
      
        
    }
    if(i>mid)
    {
        while(j<=ub)
        {
            b[k++] = a[j++];
           
        }
    }
    else {
        while(i<=mid)
        {
            b[k++] = a[i++];
          
        }
    }
    for(k=lb;k<=ub;k++){
        a[k] = b[k];
    }
}
void mergesort(int a[],int lb,int ub)
{
    int mid;
    if(lb<ub)
    {
       mid = (lb+ub)/2;
       mergesort(a,lb,mid);
       mergesort(a,mid+1,ub);
       merge(a,lb,mid,ub);
    }
}
int main()
{
    int a[10],n,i;
     printf("Enter the number of elements\n");
    scanf("%d",&n);
    printf("Elements is :\n");
    for(i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    mergesort(a,0,n-1);  
    for(i=0;i<n;i++)
    {
         printf("%d\t",a[i]);
    }
    return 0;
}
