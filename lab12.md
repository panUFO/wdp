###Lab12
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-12/index.html

```sh
#include <stdio.h>

int bit_liczby(int numer, int liczba)
{
	return (liczba&(1<<(numer)))?1:0;
}

int main()
{
//	char c;
//	int i;
//	double x;
//	int tab[100];

//	printf("char:\t\t%i\nint:\t\t%i\ndouble:\t\t%i\nint[100]:\t%i\n",
//		sizeof(c), sizeof(i), sizeof(x), sizeof(tab));

	int i;
	int n;

	scanf("%i", &n);

	for (i=sizeof(n)*8-1; i>=0; i--) {
		printf("%i", bit_liczby(i, n));
		if (i%8==0) printf(" ");
	}

	printf("\n");

	return 0;
}

```
