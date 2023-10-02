# Divide and Conquer Algorithm - Binary Search

The **divide and conquer algorithm** is a problem-solving technique where a problem is divided into smaller subproblems of the same type, solved independently, and then combined to find the final solution. This technique is often used in various computer science and mathematical algorithms.

## Concept of Divide and Conquer
1. **Divide**: Break the problem into smaller, more manageable subproblems.
2. **Conquer**: Solve each subproblem independently.
3. **Combine**: Combine the solutions of the subproblems to obtain the final solution to the original problem.

## Example 1 : Binary Search (Divide and Conquer)

Let's implement a classic divide and conquer algorithm: Binary Search. Binary Search is used to find a specific element in a sorted array efficiently.

### C++ Code for Binary Search

```cpp
#include<bits/stdc++.h>
using namespace std;


// Function to perform Binary Search
int binarySearch(const vector<int>& arr, int target, int left, int right) {
    if (left <= right) {
        int mid = left + (right - left) / 2;

        // If the target is found at the middle
        if (arr[mid] == target) {
            return mid;
        }

        // If the target is in the left half
        if (arr[mid] > target) {
            return binarySearch(arr, target, left, mid - 1);
        }

        // If the target is in the right half
        return binarySearch(arr, target, mid + 1, right);
    }

    // Element not found in the array
    return -1;
}

int main() {
    vector<int> arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    int target = 5;

    int result = binarySearch(arr, target, 0, arr.size() - 1);

    if (result != -1) {
        cout << "Element found at index: " << result << endl;
    } else {
        cout << "Element not found in the array." << endl;
    }

    return 0;
}
```


## Example 2 : Calculating Exponentiation (Divide and Conquer)

Let's implement another classic divide and conquer algorithm: calculationg exponentiation.

```cpp
#include<bits/stdc++.h>
using namespace std;

bool isEven(int a){
    return a%2==0;
}

int Fpow(int a, int b){
    if(b==0){
        return 1;
    }

    int half=Fpow(a,b/2);

    if(isEven(b)==true){
        return half*half;
    }else{
        return a*half*half;
    }
}

int main(){
    int b,n;
    cin>>b>>n;

    cout<<Fpow(b,n)<<endl;
    return 0;
}
```

The time complexity of this Fpow() function is O(log n).
