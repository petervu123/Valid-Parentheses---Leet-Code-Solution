#include <iostream>
#include <stack>
#include <string>
using namespace std;

class Solution {
public:
    bool isValid(string s) {
        stack<char> st;
        for (int i = 0; i < s.length(); i++) {
            if (s[i] == '(') {
               st.push(s[i]); 
            }
            else if (s[i] == '{') {
               st.push(s[i]); 
            }
            else if (s[i] == '[') {
               st.push(s[i]); 
            }
            else if (s[i] == ')') {
                if (st.empty()) {
                return false;
               }
               else if (st.top() != '(') {
                return false;
               }
               st.pop();
            }
            else if (s[i] == '}') {
                if (st.empty()) {
                return false;
               }
               else if (st.top() != '{') {
                return false;
               }
               st.pop();
            }
            else if (s[i] == ']') {
                if (st.empty()) {
                return false;
               }
               else if (st.top() != '[') {
                return false;
               }
               st.pop();
            }
        }
        return st.empty();
    }
};
