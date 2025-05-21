# Ex27 Kruskal’s Algorithm
## DATE: 21-05-2025
## AIM:
To write a C program to implement Kruskal's Algorithm for finding minimum cost

## Algorithm
1. Input the Graph 
2. Sort the Edges
3. Initialize Disjoint Sets
4. Build the MST  
5. Output the Result  

## Program:
```
/*
Program to implement Kruskal's Algorithm
Developed by: Divya R V
RegisterNumber:  212223100005
*/
```
```
 #include <stdio.h>
    #include <stdlib.h>
    int i,j,k,a,b,u,v,n,ne=1;
    int min,mincost=0,cost[9][9],parent[9];
    int find(int);
    int uni(int,int);
    int main()
    {
          scanf("%d",&n);
          for(i=1;i<=n;i++)
     {
     for(j=1;j<=n;j++)
     {
     scanf("%d",&cost[i][j]);
     if(cost[i][j]==0)
     cost[i][j]=999;
     }
     }
         while(ne < n)
     {
     for(i=1,min=999;i<=n;i++)
     {
     for(j=1;j <= n;j++)
     {
     if(cost[i][j] < min)
     {
     min=cost[i][j];
     a=u=i;
     b=v=j;
     }
     }
     }
     u=find(u);
     v=find(v);
     if(uni(u,v))
     {
     printf("%d edge (%d,%d) =%d\n",ne++,a,b,min);
     mincost +=min;
     }
     cost[a][b]=cost[b][a]=999;
     }
     printf("Minimum cost = %d\n",mincost);
     return 0;
       }
    
    // Text your code here for find() and uni()
    int find(int i)
    {
        while(parent[i])
        i=parent[i];
        return i;
    }
    int uni(int i, int j)
    {
        if(i!=j)
        {
            parent[j]=i;
            return 1;
        }
        return 0;
    }

```
## Output:

![image](https://github.com/user-attachments/assets/7e8fbecd-2cf9-4f2a-b824-1470dec95357)


## Result:
Thus, the C program to implement Kruskal's Algorithm for finding minimum cost is implemented successfully.
