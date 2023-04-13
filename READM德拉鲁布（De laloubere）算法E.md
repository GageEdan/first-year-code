#include<stdio.h>
#define x 100
#define y 100
int main() {
	int n = 0;
	while (1) {
		printf("请输入n的值");
		scanf("%d", &n);
		int a[x][y] = { 0 };
		a[0][n / 2] = 1;
		//printf("%d", a[0][1]);
		for (int i = 1; i <= n * n; i++) {
			//printf("%d", a[0][1]);
			for (int m = 0; m < n; m++) {
				for (int l = 0; l < n; l++) {

					if (a[m][l] == i) {
						if (m == 0 && l == n - 1) {
							if (a[n - 1][0] == 0) {
								a[n - 1][0] = i + 1;
							}
							else {
								a[m + 1][l] = i + 1;
							}
						}
						if (m == 0 && l != n - 1) {
							if (a[n - 1][l + 1] == 0) {
								a[n - 1][l + 1] = i + 1;
							}
							else {
								a[m + 1][l] = i + 1;
							}
						}
						if (m != 0 && l == n - 1) {
							if (a[m - 1][0] == 0) {
								a[m - 1][0] = i + 1;
							}
							else {
								a[m - 1][l] = i + 1;
							}
						}
						if (m != 0 && l != n - 1) {
							if (a[m - 1][l + 1] == 0) {
								a[m - 1][l + 1] = i + 1;
							}
							else {
								a[m + 1][l] = i + 1;
							}
						}
					}
				}
			}
		}
		for (int i = 0; i < n; i++) {
			printf("\n");
			for (int j = 0; j < n; j++) {
				printf("%3d", a[i][j]);
			}
		}
		printf("\n\n");
	}
	return 0;
}
