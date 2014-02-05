###LAB5
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-05/index.html

1\.Wczytujący tablicę liczb rzeczywistych i drukujący zestawienie, ile w niej jest liczb ujemnych, ile zer i ile liczb dodatnich. <br />
Uwaga: Deklaracja tablicy liczb rzeczywistych ma postać   double tab[n]; . Należy pamiętać, że niezależnie od typu elementów tablicy, jej indeksy są zawsze całkowite. <br />

```sh
#include <stdio.h>

int main()
{
	int neg=0;
	int zeros=0;
	int pos=0;
	int n, i;

	scanf("%i", &n);
	double tab[n];

	for (i=0;i<n;i++) {
		scanf("%lf", &tab[i]);
	}

	for (i=0;i<n;i++) {
		if (tab[i]<0)
			neg++;
		else if (tab[i]>0)
			pos++;
		else
			zeros++;
	}

	printf("<0: %d\n=0: %d\n>0: %d\n", neg, zeros, pos);

	return 0;
}
```

2\.Wczytujący kolejno dwie tablice liczb rzeczywistych (najpierw jedną, potem drugą) tej samej długości i drukujący ich iloczyn skalarny <br />

```sh
#include <stdio.h>

int main()
{
	int n, i;
	double mul=0;

	printf("Liczba elementow: ");
	scanf("%i", &n);

	double a[n], b[n];

	printf("Pierwsza tablica:\n");
	for (i=0; i<n; i++) {
		printf("a[%i]=", i);
		scanf("%lf", &a[i]);
	}

	printf("Druga tablica:\n");
	for (i=0; i<n; i++) {
		printf("b[%i]=", i);
		scanf("%lf", &b[i]);
	}

	for (i=0; i<n; i++) {
		mul+=a[i]*b[i];
	}

	printf("Iloczyn: %lf\n", mul);

	return 0;
}
```

3\.Wczytujący dwie tablice liczb rzeczywistych tej samej długości i drukujący wynik ich porównania leksykograficznego.

```sh
#include <stdio.h>

int main()
{
	int n,i;

	printf("DĹ‚ugoĹ›Ä‡ tablic: ");
	scanf("%i", &n);

	double a[n],b[n];

	printf("Pierwsza tablica:\n");
	for (i=0; i<n; i++) {
		printf("a[%i]=", i);
		scanf("%lf", &a[i]);
	}

	printf("Druga tablica:\n");
	for (i=0; i<n; i++) {
		printf("b[%i]=", i);
		scanf("%lf", &b[i]);
	}

	i=0;
	while (i<n-1 && a[i]==b[i])
		i++;

	if (a[i]<b[i])
		printf("a<b");
	else if (a[i]>b[i])
		printf("a>b");
	else
		printf("a=b");

	printf("\n");

	return 0;
}
```

4\.Wczytujący kilka takich tablic jak w Zad.3 i drukujący największą (leksykograficznie) z nich.

```sh
#include <stdio.h>

int main()
{
	int n,m,i,j;

	printf("Ilosc tablic: ");
	scanf("%i", &n);

	printf("Dlugosc tablic: ");
	scanf("%i", &m);

	double a[m], max[m];

	for (j=0; j<m; j++) {
		printf("tab0[%i]=", j);
		scanf("%lf", &max[j]);
	}

	for (i=1; i<n; i++) {
		printf("Tablica %i:\n", i);
		for (j=0; j<m; j++) {
			printf("tab%i[%i]=", i, j);
			scanf("%lf", &a[j]);
		}

		j=0;
		while (j<n-1 && a[j]==max[j])
			j++;

		if (a[j]>max[j])
			for (j=0; j<m; j++)
				max[j]=a[j];
	}

	for (i=0; i<m; i++) {
		printf("tab[%i]=%lf\n", i, max[i]);
	}

	return 0;
}
```
