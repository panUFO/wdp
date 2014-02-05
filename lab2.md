###LABORATORIUM 2
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-02/index.html

1\.Napisać i uruchomić program w C, który wczytuje dwie liczby rzeczywiste x i y, a następnie drukuje informację, jaki kolor na poniższym rysunku ma punkt o współrzędnych (x, y):
```sh
#include <stdio.h>

int main() {
	double x,y;
	char* kolor;

	printf("x: ");
	scanf("%lf", &x);
	printf("y: ");
	scanf("%lf", &y);

	if (y>-x+6 && x>0 && y>0) {
		kolor="ciemny";
	} else if (y<-x+6 && x<0 && y>0) {
		kolor="ciemny";
	} else if (y<-x+6 && x>0 && y<0) {
		kolor="ciemny";
	} else {
		kolor="jasny";
	}

	printf("%s", kolor);

	printf("\n");
	return 0;
}
```
2\.Napisać i uruchomić program w C, który wczytuje liczbę naturalną n i drukuje wartość sumy kwadratów 1^2 + 2^2 + 3^2 + . . . + n^2
```sh
#include <stdio.h>

int main() {
	int n, i;
	int wynik=0;

	printf("n: ");
	scanf("%i", &n);

	for (i=1; i<n+1; i++) {
		wynik += i*i;
	}

	printf("1^2 + 2^2 + ... + n^2 = %i", wynik);

	printf("\n");
	return 0;
}
```
3\.Napisać i uruchomić program w C, który wczytuje liczbę naturalną n i drukuje kolejne cyfry zapisu liczby n w ósemkowym systemie pozycyjnym, w kolejności od najmniej znaczącej.
Wskazówka:
Ostatnią cyfrą ósemkowego rozwinięcia liczby n jest n%8, czyli reszta z dzielenia n przez 8. Wszystkie poprzedzające cyfry ósemkowe składają się na ósemkowy zapis ilorazu całkowitego  n/8 .

```sh
#include <stdio.h>

int main() {
	int n;

	printf("n: ");
	scanf("%i", &n);

	do {
		printf("%i\n", n%8);
		n/=8;
	} while (n>0);

	printf("\n");
printf("Press any key to continue...\n")
getchar();
	return 0;
}
```
4\.Napisać i uruchomić program w C, który wczytuje:
*liczbę cyfr ósemkowych k,
*kolejne k cyfr ósemkowych c1,c2,c3, . . . ,ck
*i drukuje liczbę naturalną wyrażoną tymi cyframi; czyli liczbę
*(...((c1*8 + c2 )*8 + c3 )*8 + ... )*8 + ck

```sh
#include <stdio.h>

int main() {
	int k,i,c;
	int wynik=0;

	printf("k: ");
	scanf("%i", &k);

	for (i=0; i<k; i++) {
		printf("c%i: ", i+1);
		scanf("%i", &c);
		wynik*=8;
		wynik+=c;
	}

	printf("%i", wynik);

	printf("\n");
	return 0;
}
```
