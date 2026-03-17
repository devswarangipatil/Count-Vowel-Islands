# Count-Vowel-Islands

You are given a string s of length n. A vowel is defined as any of the characters a,e,i,o,u (only lowercase).

An island of vowels is a contiguous group of one or more vowels such that the characters immediately before and after the group (if they exist) are consonants.

Your task is to determine the total number of such vowel islands present in the string.

Input-
The first line contains a single integern — the length of the string.
The second line contains a string s onsisting ofn lowercase English letters.

Output-
Print a single integer — the number of vowel islands in the string.

Constraints-
1≤n≤10^5
s[i]∈a,b,c,…,z

#include <iostream>
using namespace std;

bool isVowel(char c) {
    return (c=='a' || c=='e' || c=='i' || c=='o' || c=='u');
}

int main() {
    int n;
    cin >> n;

    string s;
    cin >> s;

    int count = 0;

    for(int i = 0; i < n; i++) {
        if(isVowel(s[i])) {
            if(i == 0 || !isVowel(s[i - 1])) {
                count++;
            }
        }
    }

    cout << count;
    return 0;
}
