# crispy-waddle
import random
n=int(input())
l=[["O"for x in range(n)]for y in range(n)]
for x in range(len(l)):
    for y in range(len(l)):
      l[x][x]="X"
u=1
while u!=0:
    u=0
    for x in range(n):
      for y in range(x,n):
        y1=l[y].index("X")
        x1=l[x].index("X")
        if (  x-x1==y-y1 or x+x1==y+y1 ) and x!=y:
         c = random.randint(x,n-1)
         l[y],l[c]=l[c],l[y]
         u+=1
for x in range(len(l)):
         for i in range(len(l)):
             print(l[x][i], end=" ")
         print()
