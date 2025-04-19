# KMP算法及求Next函数
```C++
#include <vector>
#include <string>
using namespace std;

// 构建部分匹配表(实际上就是求next数组）
vector<int> buildPartialMatchTable(const string& pattern) {
    vector<int> pmt(pattern.size(), 0);
    int len = 0;  // 当前最长公共前后缀长度
    
    for (int i = 1; i < pattern.size(); ) {
        if (pattern[i] == pattern[len]) {
            pmt[i++] = ++len;
        } else {
            if (len != 0) {
                len = pmt[len - 1];
            } else {
                pmt[i++] = 0;
            }
        }
    }
    return pmt;
}

// KMP搜索算法
int kmpSearch(const string& text, const string& pattern) {
    vector<int> pmt = buildPartialMatchTable(pattern);
    int i = 0, j = 0;  // i: text索引, j: pattern索引
    
    while (i < text.size() && j < pattern.size()) {
        if (text[i] == pattern[j]) {
            i++;
            j++;
        } else {
            if (j != 0) {
                j = pmt[j - 1];
            } else {
                i++;
            }
        }
    }
    
    return j == pattern.size() ? i - j : -1;  // 返回匹配起始位置，未找到返回-1
}

int main() {
    string text = "ABABDABACDABABCABAB";
    string pattern = "ABABCABAB";
    int pos = kmpSearch(text, pattern);
    // 输出: Pattern found at index: 10
    cout << "Pattern found at index: " << pos << endl;
    return 0;
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ0MTU0NTMwMyw4Mzg1NDMyNzNdfQ==
-->