###LAB3 
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-03/index.html

1\.Napisać i uruchomić program w C, który wczytuje <br />
liczbę całkowitą n≥0 , a następnie <br />
n liczb rzeczywistych (double) <br />
i drukuje te liczby w trzech kolumnach w taki sposób, żeby zachować krycie (kropka dziesiętna zawsze w tych samych kolumnach.<br />

```sh
#include <stdio.h>

int main()
{
	int n,i;
	double a;

	scanf("%i", &n);

	printf(" kol.1 | kol.2  | kol.3 \n");
	printf("-------+--------+-------\n");
	for (i=0;i<n;i++) {
		scanf("%lf", &a);
		printf("%6.2lf", a);
		if (i%3 == 2)
			printf("\n");
		else
			printf(" | ");
	}

	while (i%3 == 1) {
		printf("       |\n");
		i++;
	}

	return 0;
}

```
2\.Napisać i uruchomić program w C, który drukuje pełną tabliczkę mnożenia (czyli tablicę iloczynów pojedynczych cyfr) dla systemu dziesiętnego. Zadbać o krycie w kolumnach liczb (por. ściąga). Postarać się, żeby program wcale nie używał mnożenia. <br />
Wskazówka: <br />
Żeby program wydrukował liczbę całkowitą na polu o długości 2 znaki, należy w komendzie printf użyć formatu "%2i" . <br />

```
#include <stdio.h>

int main()
{
	int n;
	int i,j,k;
	int mul;

	scanf("%i", &n);

	printf("//");
	for (i=0;i<n+2;i++) {
		printf("=====");
	}
	printf("\\\\\n");

	printf("||    ||");
	for (i=0;i<=n;i++) {
		printf(" %2i |", i);
	}
	printf("|\n");

	printf("||====+");
	for (i=0;i<=n;i++) {
		printf("+====");
	}
	printf("||\n");

	for (j=0;j<=n;j++) {
		mul=0;
		printf("|| %2i ||", j);
		for (k=0;k<=n;k++) {
			printf(" %2i |", mul);
			mul+=j;
		}
		printf("|\n");
		if (j!=n) {
			printf("||----+");
			for (i=0;i<=n;i++) {
				printf("+----");
			}
			printf("||\n");
		}
	}

	printf("\\\\");
	for (i=0;i<n+2;i++) {
		printf("=====");
	}
	printf("//\n");
	return 0;
}

```

3\.Napisać i uruchomić program w C, który wczytuje liczbę naturalną n i drukuje sumę potęg <br />
1^1 + 2^2 + 3^3 + . . . + n^n <br />
Wskazówka: <br />
Potrzebne jest zagnieżdżenie pętli for. Zewnętrzna pętla powinna dodawać do sumy kolejny składnik. Wewnętrzna powinna wyliczać potęgę ii dla kolejnych i od 1 do n <br />

```sh
#include <stdio.h>

int main()
{
	int n,i,j;
	int sum=0;
	int pow;

	scanf("%i", &n);

	for (i=1;i<=n;i++) {
		pow=i;
		for (j=1;j<i;j++) {
			pow*=i;
		}
		sum+=pow;
	}

	printf("%i\n", sum);

	return 0;
}
```

4\.Napisać i uruchomić program w C, który wczytuje liczbę naturalną n i drukuje kolejne cyfry zapisu liczby n w szesnastkowym systemie pozycyjnym, w kolejności od najmniej znaczącej. <br />
```sh
#include <stdio.h>

int main()
{
	int n;
	int i;

	scanf("%i", &n);

	do {
		i=n%16;
		if (i<10)
			printf("%i\n", i);
		else
			printf("%c\n", (char)(i+55));
		n/=16;
	} while (n>0);

	printf("\n");

	return 0;
}
```

