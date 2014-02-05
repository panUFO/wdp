###LABORATORIUM 1

1\.Drukujący 50 powitań i numerującego je:
```sh
#include<stdio.h>
int main () {
int n;
for (n=0; n<50; n=n+1) {
printf("%i. CZESC!\n", n);
}
return 0;
      }  
```
2\.Podnoszącego liczbę 20 do kwadratu:
```sh
    #include<stdio.h>
      int main () {
        int n, a, b, p;
        n=0; a=1; b=0; p=20;
        while (n<p) {
          b = b+a; a = a+2; n = n+1;
        }
        printf("\n %i^2 == %i\n\n", p, b);
        return 0;
      }  
```
