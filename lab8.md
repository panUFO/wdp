### LAB8 ZAD2

```c
void sort () 
{
int i,j;
for (i=DL_ALFABETU; i>=1; i=i-1)
  for (j=1; j<i; j=j+1)
  if (liczniki [j-1] < liczniki [j])
  zamien(j-1,j);
}

void zamien (int k, int l)
{
int pom;
pom=liczniki[k];
liczniki[k]=liczniki[l];
liczniki[l]=pom;

pom=ind[k];
ind[k]=ind[l];
ind[l]=pom;
}
```
