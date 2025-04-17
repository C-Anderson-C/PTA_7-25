# PTA_7-25
# 念数字
# 输入一个整数，输出每个数字对应的拼音。当整数为负数时，先输出fu字。十个数字对应的拼音如下：


# 输入格式：输入在一行中给出一个整数，如：1234。提示：整数包括负数、零和正数。

# 输出格式：在一行中输出这个整数对应的拼音，每个数字的拼音之间用空格分开，行末没有最后的空格。如yi er san si。
```cpp

/*0: ling
1: yi
2: er
3: san
4: si
5: wu
6: liu
7: qi
8: ba
9: jiu
*/

#include <iostream>
#include <string>
#include<vector>
using namespace std;
int main() {
	vector<string>pingyin = { "ling","yi","er","san","si","wu","liu","qi","ba","jiu" };
	string num;
	cin >> num;

	if (num[0] == '-') {
		cout << "fu"<<" ";
		num = num.substr(1);
	}

	for (size_t i = 0;i < num.length();i++) {
		int digit = num[i] - '0';
		cout << pingyin[digit];
		if (i != num.length() - 1) {
			cout << " ";
		}
	}
	cout << endl;
	return 0;
}