## Mentor's LinkedIn - https://www.linkedin.com/in/prateeknarang27/

## Topic - Hashing

### Restaurant menu analogy
    - In restaurant menu items are present as key value pairs, it is similar to hashmaps

    dosa            60
    pav bhaji       60
    Chowmein        90 

### Hash Table Data Structure Operations
    - Insertion  => Time -> O(1) average
    - Search  => Time -> O(1) average
    - Remove  => Time -> O(1) average

#### Hash Table in c++ (Container types)
    - Maps and unordered_maps
    - Sets and unordered_sets
    - MultiMaps and unordered MultiMaps
    - These Containers are used in-
        - Array Problems
        - Linked List Problems
        - Sliding Window
        - Graphs

#### HashTable implementation in C++
```
#include <iostream>
#include <unordered_map>

using namespace std;

int main()
{
    unordered_map<string, int> menu;

    // Insertion O(1) time
    menu["dosa"] = 50;
    menu["idli"] = 60;
    menu["maggi"] = 20;
    menu["amul_lassi"] = 15;

    menu.insert(make_pair("burger", 55)); // similar to above lines

    // remove item from menu
    menu.erase("maggi");

    string item;
    cout << "Enter item to search\n";
    cin >> item;

    if (menu.count(item))
    {
        cout << "price of item is " << menu[item] << endl;
    }
    else
    {
        cout << item << " is unavailable or out of stock\n";
    }

    // To print full map
    for (auto val : menu)
    {
        cout << val.first << " - " << val.second << endl;
    }
}

```

#### Unordered set in C++
```
    unordered_set<int> s{10, 11, 22, 3, 44, 5, 6, 7, 8};

    // Insert in O(1)
    s.insert(20);

    // Delete in O(1)
    s.erase(10);

    // Search in O(1)
    int key;
    cin >> key;

    if (s.find(key) != s.end())
    {
        cout << "found";
    }
    else
    {
        cout << "Not found";
    }

    for (int x : s)
    {
        cout << x << " ";
    }
```

#### Questions

1. Detecting if there is a loop in linked list
        1 -> 2 -> 3 -> 4 -> 5
            |               |
            8  <-   7    <- 6 

    ```
    bool containsCycle(node *head)
    {
        unordered_map<node *, bool> hashtable;

        node *temp = head;

        while (temp != NULL)
        {
            if (hashtable.count(temp) != 0)
            {
                return true;
            }
            hashtable[temp] = true;
            temp = temp->next;
        }

        return false;
    }
    ```

    Time -> O(n) and Space -> O(n)

2. Pair Sum Problem - Find all such pairs in the array with sum = K
    Example - arr = {0,3,2,5,6,10,8,-2}
    K = 8

    Possible Solutions - 
        * Brute Force (Two loops) => O(n^2)
        * Sorting and two pointer => O(log(n)) + O(n)
        * Sorting and Binary Search => O(log(n)) + O(log(n))
        * unordered_map => O(n)

    Implementation of solution using unordered_map

    If we add all elements first and then check for other element then it will result out in duplicate results

    Solution -> Insert and check at same time

    Code -> 
    ```
    #include <iostream>
    #include <unordered_set>

    using namespace std;

    int main()
    {
        int arr[] = {-2, 0, 1, 2, 3, 5, 8, 10, 16, 2};

        int n = sizeof(arr) / sizeof(int);

        unordered_set<int> s;

        int total = 8;

        for (int i = 0; i < n; i++)
        {

            int current = arr[i];
            int element = total - current;

            if (s.find(element) != s.end())
            {
                cout << current << " , " << element << endl;
            }
            s.insert(current);
        }
    }

    ```

3. Longest Consecutive Chain

    Example -> arr = {12, 10, 3, 1, 5, 8, 4, 2, 6, 11}

    Chains are = 1,2,3,4,5,6 and 10,11,12 and 6 and 8 
    Longest chain is 1,2,3,4,5,6

    Hint -> Find the head of the chain and find the length of the chain by searching for next element