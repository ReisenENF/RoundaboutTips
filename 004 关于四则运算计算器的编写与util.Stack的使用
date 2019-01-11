static int calculate(String str) {
            int res = 0, num = 0, n = str.length();
            char op = '+';
            Stack <Integer> st = new Stack<>();
            char s[]=str.toCharArray();
            for (int i = 0; i < n; ++i) {
                if (s[i] >= '0') {
                //不是符号，在遍历中获取多位十进制数组成一个数存入num，顺便将char转为int
                    num = num * 10 + s[i] - '0';
                }
             if ((s[i] < '0' && s[i] != ' ') || i == n - 1) {
                //如果是符号且不为空格，Stack.push（）用于将传入参数推至该Stack对象的顶部，用于模拟*/运算高于+-运算的优先级
                    if (op == '+') st.push(num);
                    if (op == '-') st.push(-num);
                    if (op == '*' || op == '/') {
                        int tmp = (op == '*') ? st.peek() * num : st.peek() / num;
                        //“*/”计算完毕将结果看作整体继续推送至Stack顶端，向下计算
                        st.pop();
                        st.push(tmp);
                    }
                    op = s[i];
                    num = 0;
                }
            }
            //经过上面的for，已经将原计算式*/法算完，-为负+，因此堆上的数全部相加即可
            while (!st.empty()) {
                res += st.peek();
                st.pop();
            }
            return res;
        }
