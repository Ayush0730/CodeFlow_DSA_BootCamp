## Mentor's LinkedIn - https://www.linkedin.com/in/sumeet-malik-ab650410/

## Topic - Recursion

-> PD = PrintDecreasing

### High Level Thinking
    - Expectation
        - For PD(5), we expect it to print 5 4 3 2 1
    - Faith
        - Assume faith for smaller problem, i.e you have to trust that the function is capable of handling smaller problem
        - In this problem, we will assume PD(4) is capable of printing 4 3 2 1
    - Meet your Expectation from your faith
        - Now, we will think how can we use faith to meet expectation
        - PD(5) = 5 PD(4)
        - We get 5(print by yourself) [4 3 2 1](From faith)

## Low Level Thinking
    - Visualize your function using call stack, and run do step by step analysis
    - It helps to find base case

### Questions

1. Print Decreasing [Link](https://www.pepcoding.com/resources/online-java-foundation/introduction-to-recursion/print-decreasing-official/ojquestion)

```
#include <iostream>
using namespace std;

void printDecreasing(int n) {
  if (n == 0) {
    return;
  }
  cout << n << endl;
  printDecreasing(n - 1);
}

int main() {
  int n;
  cin >> n;
  printDecreasing(n);
}
```

2. Print Increasing [Link](https://www.pepcoding.com/resources/online-java-foundation/introduction-to-recursion/print-increasing-official/ojquestion)

```
#include<iostream>
using namespace std;

void printIncreasing(int n){
    if (n == 0) {
        return;
    }
    printIncreasing(n-1);
    cout << n << endl;
}


int main(){
    int n; cin>>n;
    printIncreasing(n);
}
```

3. Print Increasing Decreasing [Link](https://www.pepcoding.com/resources/online-java-foundation/introduction-to-recursion/print-increasing-decreasing-official/ojquestion)

```
#include<iostream>
using namespace std;

void printIncDec(int n){
    if(n == 0){
        return;
    }
    cout<<n<<endl;
    printIncDec(n-1);
    cout<<n<<endl;
}


int main(){
    int n; cin>>n;
    printIncDec(n);
}
```

Sumeet Malik Sir's Video on Greedy - [Link](https://www.youtube.com/watch?v=VT4bZV24QNo&list=TLGG-g-kz4wW-7wxMDA2MjAyMQ&t=69s)