###LAB11
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-11/index.html
Wyznacznik macierzy

```sh
#include <stdio.h>

double det(int n, double tab[n][n])
{
	if (n==1)
		return tab[0][0];

	int i,j,k;
	double sum=0;
	double tmp;
	double tab1[n-1][n-1];

	for (i=0; i<n; i++) {
		for (j=0; j<n-1; j++) {
			for (k=0; k<i; k++)
				tab1[j][k]=tab[j][k];
			for (k=i+1; k<n; k++)
				tab1[j][k-1]=tab[j][k];
		}
		tmp=tab[n-1][i]*det(n-1, tab1);
		if ((n-1+i)%2==1) tmp=-tmp;
		sum+=tmp;
	}

	return sum;
}

int main()
{
	int n;
	scanf("%i", &n);

	double tab[n][n];
	int i, j;

	for (i=0; i<n; i++)
		for (j=0; j<n; j++)
			scanf("%lf", &tab[i][j]);

	printf("%lf\n", det(n, tab));

	return 0;
}

```
