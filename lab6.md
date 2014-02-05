###LAB6
https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-06/index.html

1\.Napisać program, który potrafi wczytać dwie bardzo duże nieujemne liczby całkowite (składające się z bardzo wielu cyfr), dodać je i wydrukować wynik. Program powinien potrafić wykonać np. takie działanie: <br />
98765432109876543210987654321 + 1234567890123456789012345679 = 100000000000000000000000000000 <br />
na liczbach 30-cyfrowych. <br />

```sh
#include <stdio.h>

int main()
{
	int n, m, i, p, max;

	scanf("%i", &n);
	int a[n];

	for (i=n-1;i>=0;i--)
		scanf("%1i", &a[i]);

	scanf("%i", &m);
	int b[m];

	for (i=m-1;i>=0;i--)
		scanf("%1i", &b[i]);

	max = n>m?n:m;
	int w[max+1];

	for (i=0;i<max+1;i++)
		w[i] = 0;

	for (i=0;i<max;i++) {
		p=0;

		if (i<n)
			w[i]+=a[i];
		if (i<m)
			w[i]+=b[i];

		if (w[i]>9) {
			p = w[i]/10;
			w[i] %= 10;
		}
		w[i+1]+=p;
	}

	while (w[max]==0)
		max--;

	for (i=max;i>=0;i--)
		printf("%i", w[i]);

	printf("\n");
	return 0;
}

```

2\.W podobny sposób zrealizować pozostałe działania arytmetyczne (odejmowanie, mnożenie i dzielenie).
*odejmowanie
```sh
#include <stdio.h>

int main()
{
	int n, m, i, p, max;

	scanf("%i", &n);
	int a[n];

	for (i=n-1;i>=0;i--)
		scanf("%1i", &a[i]);

	scanf("%i", &m);
	int b[m];

	for (i=m-1;i>=0;i--)
		scanf("%1i", &b[i]);

	max = n>m?n:m;
	int w[max+1];

	for (i=0;i<max+1;i++)
		w[i] = 0;

	for (i=0;i<max;i++) {
		p=0;

		if (i<n) {
			if (n>m)
				w[i]+=a[i];
			else
				w[i]-=a[i];
		}
		if (i<m) {
			if (m>n)
				w[i]+=b[i];
			else
				w[i]-=b[i];
		}

		if (w[i]<0) {
			p = -1;
			w[i] += 10;
		}
		w[i+1]+=p;
	}

	while (w[max]==0 && max>0)
		max--;

	if (m>n)
		printf("-");

	for (i=max;i>=0;i--)
		printf("%i", w[i]);

	printf("\n");
	return 0;
}
```
