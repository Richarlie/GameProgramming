# n皇后问题
# Description

有N*N的国际象棋棋盘，要求在上面放N个皇后，要求任意两个皇后不会互杀，有多少种不同的放法
  

# 输入格式

每一个数为T，代表CASE的数量，T<=13
此后，每行一个数N（13>=N>0）

  

# 输出格式

每一个CASE，输出对应答案

  
  

# 输入样例

2
4
5

  
  

# 输出样例

2
10

```C++
#include<iostream>
#include<algorithm>
#include<vector>
#include<string>
using namespace std;

vector<int>line;
vector<int>rpos;
vector<int>lpos;
int cnt;
int N;

int isValid(int row, int k) {
	return line[k] == 0 && lpos[row - k + N - 1] == 0 && rpos[k + row] == 0;
}

void cal(int row) {
	if (row == N) {
		cnt++;
		return;
	}
	for (int k = 0; k < N; k++) {
		if (isValid(row, k)) {
			line[k] = lpos[row - k + N - 1] = rpos[k + row] = 1;
			cal(row + 1);
			line[k] = lpos[row - k + N - 1] = rpos[k + row] = 0;
		}
	}
}

int main() {
	int n;
	cin >> n;
	while (n--) {
		cin >> N;
		cnt = 0;
		line = vector<int>(N, 0);
		rpos = vector<int>(2 *N - 1, 0);
		lpos = vector<int>(2 * N - 1, 0);
		cal(0);
		cout << cnt << endl;
	}

	return 0;
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEyMTAxNTgwN119
-->