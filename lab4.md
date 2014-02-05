###LAB4 
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-04/index.html

1\.Napisać i uruchomić program w C, który wczytuje ciąg liczb naturalnych (czyli: całkowitych nieujemnych) i drukuje ten ciąg w odwrotnej kolejności. <br />
Założenia: <br />
Długość ciągu na wejściu jest programowi nieznana; to znaczy, że powinien działać dobrze na ciągach dowolnej długości, niewiększej niż, powiedzmy, 1000. Kiedy użytkownik programu skończy podawać liczby naturalne swojego ciągu, wpisuje dodatkowo liczbę -1, żeby program wiedział, że to już koniec danych i że powinien przystąpić do odwracania ciągu. <br />

```sh

```


2\.Napisać i uruchomić program w C, który wczytuje liczbę naturalną n, zamienia ją na układ ósemkowy i drukuje jej kolejne cyfry ósemkowe w zwykłej kolejności, czyli od najbardziej znaczącej.

```sh

```

3\.Program szyfr.c służy do szyfrowania tekstów litera po literze przez zastępowanie ich liczbami. Napisać własny program odszyfr.c potrafiący odszyfrować tak zapisane teksty. <br />
Założenia: <br />
Program szyfr.c potrafi zamieniać na liczby tylko małe łacińskie litery (bez polskich ogonków!) oraz znak odstępu. Wczytuje tekst do końca (jeśli z klawiatury, to znakiem końca jest Ctr-D). Na końcu zaszyfrowanego tekstu stawia liczbę -1. <br />

```sh
#include <stdio.h>

int main()
{
	char klucz[27];
	int v;

	klucz[0] = 's';	klucz[9]  = 'w'; klucz[18] = 'k';
	klucz[1] = 'i';	klucz[10] = 'y'; klucz[19] = 'r';
	klucz[2] = 'n';	klucz[11] = 'c'; klucz[20] = 'j';
	klucz[3] = 'h';	klucz[12] = ' '; klucz[21] = 'u';
	klucz[4] = 'm';	klucz[13] = 'b'; klucz[22] = 'd';
	klucz[5] = 't';	klucz[14] = 'q'; klucz[23] = 'g';
	klucz[6] = 'p';	klucz[15] = 'x'; klucz[24] = 'o';
	klucz[7] = 'a';	klucz[16] = 'e'; klucz[25] = 'f';
	klucz[8] = 'l';	klucz[17] = 'v'; klucz[26] = 'z';

	scanf("%i", &v);

	while (v!=-1) {
		printf("%c", klucz[v]);
		scanf("%i", &v);
	}

	printf("\n");

	return 0;
}
```

4\.Napisać jakiś własny program szyfrujący litery za pomocą innych liter, oraz do niego program odszyfrowujący. <br />
Szyfr <br />
```sh
#include <stdio.h>

int main()
{
	char key[27];
	char c;

	key[0]='t';	key[9] ='b';	key[18]='p';
	key[1]='h';	key[10]='r';	key[19]='s';
	key[2]='e';	key[11]='o';	key[20]='v';
	key[3]=' ';	key[12]='w';	key[21]='l';
	key[4]='q';	key[13]='n';	key[22]='a';
	key[5]='u';	key[14]='f';	key[23]='z';
	key[6]='i';	key[15]='x';	key[24]='y';
	key[7]='c';	key[16]='j';	key[25]='d';
	key[8]='k';	key[17]='m';	key[26]='g';

	scanf("%c", &c);

	while (c!='0') {
		if (c==' ')
			printf("%c", key[0]);
		else
			printf("%c", key[(int)c-96]);
		scanf("%c", &c);
	}

	printf("0\n");

	return 0;
}

```

ODSZYFR

```sh
#include <stdio.h>

int main()
{
	char klucz[27];
	char c;

	klucz[0] = 't';	klucz[9]  = 'b'; klucz[18] = 'p';
	klucz[1] = 'h';	klucz[10] = 'r'; klucz[19] = 's';
	klucz[2] = 'e';	klucz[11] = 'o'; klucz[20] = 'v';
	klucz[3] = ' ';	klucz[12] = 'w'; klucz[21] = 'l';
	klucz[4] = 'q';	klucz[13] = 'n'; klucz[22] = 'a';
	klucz[5] = 'u';	klucz[14] = 'f'; klucz[23] = 'z';
	klucz[6] = 'i';	klucz[15] = 'x'; klucz[24] = 'y';
	klucz[7] = 'c';	klucz[16] = 'j'; klucz[25] = 'd';
	klucz[8] = 'k';	klucz[17] = 'm'; klucz[26] = 'g';

	scanf("%c", &c);

	while (c!='0') {
		
		scanf("%c", &c);
	}

	printf("\n");

	return 0;
}
```
