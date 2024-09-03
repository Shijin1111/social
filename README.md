# <span style="color: #e03e2d;">TRANSPOSE , REVERSE OF MATRIX</span>

```c
Transpose the matrix 
 Transpose the matrix
        for (int i = 0; i < n; ++i) 
{
            for (int j = i + 1; j < n; ++j) 
{
                swap(matrix[i][j], matrix[j][i]);
               }
        } 
(when u swap make sure to put j=i+1; )
Reverse each row
        for (int i = 0; i < n; ++i) {
            reverse(matrix[i].begin(), matrix[i].end());
        }
    }
};
```

### <span style="color: #2dc26b;">(when u swap make sure to put j=i+1; )</span>

* * *
### use #include<numeric> for mathematical funtions.(math.h may not work);
examples of this fns:  gcd(16,4) gives 4;
### rand() is used to get a random number
## int randomNumber = rand();


# <span style="color: #e03e2d;">STRING METHODS IN C++</span>

```c
In C++, strings are managed through the Standard Template Library (STL), which provides a comprehensive set of methods to manipulate and work with string data efficiently. Here's an overview of some commonly used string methods in C++:

### Basic String Operations

1. **Include the Necessary Header**
   ```cpp
   #include <string>
```

2.  **Declare and Initialize Strings**
    
    ```cpp
    std::string s1 = "Hello"; // Initializing with a string literal
    std::string s2("World"); // Initializing with a constructor
    std::string s3; // Initializing an empty string
    ```
    

### Accessing Characters

- **Accessing Individual Characters**
    
    ```cpp
    char ch = s1[0]; // Accessing character at index 0 (no bounds checking)
    char ch2 = s1.at(1); // Accessing character at index 1 (with bounds checking)
    ```
    
- **Iterating Over Characters**
    
    ```cpp
    for (char ch : s1) {
        std::cout << ch << " ";
    }
    ```
    

### String Length and Capacity

- **Length**
    
    ```cpp
    int len = s1.length(); // Returns the number of characters in the string
    int size = s1.size(); // Equivalent to length(), returns the number of characters
    ```
    
- **Capacity**
    
    ```cpp
    int capacity = s1.capacity(); // Returns the allocated storage capacity of the string
    ```
    

### String Manipulation

- **Appending**
    
    ```cpp
    s1 += " World"; // Append a string literal
    s1.append(" Universe"); // Append using the append method
    ```
    
- **Inserting**
    
    ```cpp
    s1.insert(6, " Beautiful"); // Insert at position 6
    ```
    
- **Erasing**
    
    ```cpp
    s1.erase(6, 10); // Erase 10 characters starting from position 6
    ```
    
- **Replacing**
    
    ```cpp
    s1.replace(6, 10, "Wonderful"); // Replace 10 characters starting from position 6 with "Wonderful"
    ```
- **isalnum(ch)**
  - This function checks if the character ch is alphanumeric (either a letter or a digit). It returns a non-zero value (true) if ch is alphanumeric and zero (false) otherwise.

### Searching and Finding

- **Finding Substrings**

  Different in vector search.
    ```cpp
    size_t pos = s1.find("World"); // Find the first occurrence of "World" in s1
    if (pos != std::string::npos) {
        std::cout << "Found at position: " << pos << std::endl;
    }
    ```
    
- **Counting Occurrences**
    
    ```cpp
    int count = std::count(s1.begin(), s1.end(), 'o'); // Count occurrences of 'o' in s1
    ```
    

### Substring Extraction

- **Substr**
    
    ```cpp
    std::string sub = s1.substr(6, 5); // Extract substring starting from position 6 of length 5
    ```
    
    <span style="color: #2dc26b;">second parameter is the length.not the ending index.</span>
    

### Conversion

- **C-Style String Conversion**
    
    ```cpp
    const char* cstr = s1.c_str(); // Convert std::string to const char*
    ```
    
- **String to Integer**
    
    ```cpp
    int num = std::stoi("123"); // Convert string to integer
    ```
    
    <span style="color: #2dc26b;">to convert a char of a string you have to do s[i]-'0' This way, you correctly convert the character `s[i]` to its corresponding integer value and then compare it to `10`.</span>
    
- **Integer to String**
    
    ```cpp
    std::string str = std::to_string(123); // Convert integer to string
    ```
    

### Comparing Strings

- **Comparison**
    
    ```cpp
    if (s1 == s2) {
        std::cout << "Strings are equal" << std::endl;
    } else {
        std::cout << "Strings are not equal" << std::endl;
    }
    ```
    
- **Lexicographical Comparison**
    
    ```cpp
    if (s1.compare(s2) == 0) {
        std::cout << "Strings are equal" << std::endl;
    }
    ```
    

# <span style="color: #e03e2d;">SETS IN C++</span>

```C
In C++, sets are part of the Standard Template Library (STL) and are used to store unique elements in a specific order. The `set` and `unordered_set` containers provide efficient means to perform operations such as insertion, deletion, and lookup.

### `std::set`

The `std::set` container stores unique elements following a specific order (typically sorted). Here are some basic operations:

#### Including the Necessary Header
```cpp
#include <set>
```

#### Creating a Set

```cpp
std::set<int> mySet;
```

#### Inserting Elements

```cpp
mySet.insert(1);
mySet.insert(3);
mySet.insert(2);
```

#### Checking for Existence

```cpp
if (mySet.find(2) != mySet.end()) {
    std::cout << "2 is in the set" << std::endl;
}
```

#### Removing Elements

```cpp
mySet.erase(1);
```

#### Iterating Over Elements

```cpp
for (auto it = mySet.begin(); it != mySet.end(); ++it) {
    std::cout << *it << " ";
}
// Output: 2 3
```

or just use this:

```c++
for (int elem : mySet) {
        cout << elem << " ";
    }
```

### `std::unordered_set`

The `std::unordered_set` container also stores unique elements but does not maintain any specific order. It typically provides faster average time complexity for insertions, deletions, and lookups due to hashing.

#### Including the Necessary Header

```cpp
#include <unordered_set>
```

#### Creating an Unordered Set

```cpp
std::unordered_set<int> myUnorderedSet;
```

#### Inserting Elements

```cpp
myUnorderedSet.insert(1);
myUnorderedSet.insert(3);
myUnorderedSet.insert(2);
```

#### Checking for Existence

```cpp
if (myUnorderedSet.find(2) != myUnorderedSet.end()) {
    std::cout << "2 is in the unordered set" << std::endl;
}
```

#### Removing Elements

```cpp
myUnorderedSet.erase(1);
```

#### Iterating Over Elements

```cpp
for (auto it = myUnorderedSet.begin(); it != myUnorderedSet.end(); ++it) {
    std::cout << *it << " ";
}
// Output: The order can be different each time
```

### Example: Using `std::set` in a Function

Here is an example of a function that uses `std::set` to find the length of the longest substring without repeating characters, as discussed previously:

```cpp
#include <iostream>
#include <set>
#include <string>
#include <algorithm> // For max

class Solution {
public:
    int lengthOfLongestSubstring(std::string s) {
        std::set<char> charSet;
        int left = 0, right = 0, maxLength = 0;

        while (right < s.size()) {
            if (charSet.find(s[right]) == charSet.end()) {
                charSet.insert(s[right]);
                maxLength = std::max(maxLength, right - left + 1);
                right++;
            } else {
                charSet.erase(s[left]);
                left++;
            }
        }

        return maxLength;
    }
};

int main() {
    Solution sol;
    std::string s = "abcabcbb";
    std::cout << "Length of longest substring without repeating characters: " 
              << sol.lengthOfLongestSubstring(s) << std::endl;
    return 0;
}
```

### Example: Using `std::unordered_set` in a Function

Here is the same function using `std::unordered_set` for potentially better performance with average cases:

```cpp
#include <iostream>
#include <unordered_set>
#include <string>
#include <algorithm> // For max

class Solution {
public:
    int lengthOfLongestSubstring(std::string s) {
        std::unordered_set<char> charSet;
        int left = 0, right = 0, maxLength = 0;

        while (right < s.size()) {
            if (charSet.find(s[right]) == charSet.end()) {
                charSet.insert(s[right]);
                maxLength = std::max(maxLength, right - left + 1);
                right++;
            } else {
                charSet.erase(s[left]);
                left++;
            }
        }

        return maxLength;
    }
};

int main() {
    Solution sol;
    std::string s = "abcabcbb";
    std::cout << "Length of longest substring without repeating characters: " 
              << sol.lengthOfLongestSubstring(s) << std::endl;
    return 0;
}
```

### Summary

- **`std::set`**: Stores unique elements in sorted order. Suitable when order is important.
- **`std::unordered_set`**: Stores unique elements with no specific order. Generally faster for insertions, deletions, and lookups.

Choose `std::set` or `std::unordered_set` based on your specific requirements regarding element order and performance characteristics.

# <span style="color: #e03e2d;">VECTOR ARRAY METHODS IN C++</span>

### Initialization and Construction

```C++
1. **Declaration and Initialization**:
   ```cpp
   std::vector<int> nums;                // Empty vector of integers
   std::vector<int> nums = {1, 2, 3};    // Vector initialized with elements
   std::vector<int> nums(5, 10);         // Vector with 5 elements initialized to 10
```

2.  **Size and Capacity**:
    
    - `size()`: Returns the number of elements in the vector.
    - `capacity()`: Returns the current storage capacity of the vector.
    - `empty()`: Returns `true` if the vector is empty.
    
    ```cpp
    std::vector<int> nums = {1, 2, 3};
    nums.size();        // Returns 3
    nums.capacity();    // Depends on implementation, typically >= 3
    nums.empty();       // Returns false
    ```
    
    - `reserve(size_t n)`: Increases the capacity of the vector to at least `n` elements.
    - `shrink_to_fit()`: Reduces the capacity to fit the current size of the vector.
    
    ```cpp
    nums.reserve(10);   // Reserves storage for at least 10 elements
    nums.shrink_to_fit();// Reduces capacity to fit size
    ```
    

### Element Access

3.  **Accessing Elements**:
    
    - Direct access using index (`operator[]`) or with bounds checking (`at()`):
    
    ```cpp
    std::vector<int> nums = {1, 2, 3};
    nums[0];            // Accesses first element (1)
    nums.at(1);         // Accesses second element (2) with bounds checking
    ```
    
    - Access to first and last elements:
    
    ```cpp
    nums.front();       // Returns reference to the first element (1)
    nums.back();        // Returns reference to the last element (3)
    ```
    

### Modification

4.  **Adding and Removing Elements**:
    
    - Adding elements:
        - `push_back(value)`: Adds `value` to the end of the vector.
        - `insert(iterator pos, value)`: Inserts `value` before the element at position `pos`.
        - <span style="color: #2dc26b;">nums.begin() must for insert.it won't work with insert(2, 4);</span>
    
    ```cpp
    std::vector<int> nums = {1, 2, 3};
    nums.push_back(4);        // Adds 4 to the end: {1, 2, 3, 4}
    nums.insert(nums.begin() + 1, 5); // Inserts 5 at index 1: {1, 5, 2, 3, 4}
    ```
    
    - Removing elements:
        - `pop_back()`: Removes the last element.
        - `erase(iterator pos)`: Removes the element at position `pos`.
    
    ```cpp
    nums.pop_back();         // Removes 4: {1, 5, 2, 3}
    nums.erase(nums.begin() + 2); // Removes element at index 2: {1, 5, 3}
    ```
    
    - `clear()`: Removes all elements from the vector.
    
    ```cpp
    nums.clear();            // Empties the vector
    ```
    
5.  **Modifying Elements**:
    
    - Direct assignment:
    
    ```cpp
    std::vector<int> nums = {1, 2, 3};
    nums[1] = 10;          // Assigns 10 to the second element: {1, 10, 3}
    ```
    

### Iteration and Range-Based For Loop

6.  **Iterating Over Elements**:
    
    - Using index-based loops, iterators, and range-based for loops:
    
    ```cpp
    std::vector<int> nums = {1, 2, 3};
    
    // Index-based loop
    for (size_t i = 0; i < nums.size(); ++i) {
        std::cout << nums[i] << " ";
    }
    
    // Iterator-based loop
    for (auto it = nums.begin(); it != nums.end(); ++it) {
        std::cout << *it << " ";
    }
    
    // Range-based for loop (C++11 and later)
    for (int num : nums) {
        std::cout << num << " ";
    }
    ```
    

### Utility Functions

7.  **Sorting**:
    
    - Sorting elements in ascending order using `std::sort`:
    
    ```cpp
    std::vector<int> nums = {3, 1, 4, 1, 5, 9, 2};
    std::sort(nums.begin(), nums.end());  // Sorts: {1, 1, 2, 3, 4, 5, 9}
    ```
    
8.  **Searching**:

    You have to use begin() and end()!!!!!
    - Searching for an element using `std::find`:
        
        ```cpp
        auto it = std::find(nums.begin(), nums.end(), 4); // Finds first occurrence of 4
        if (it != nums.end()) {
            std::cout << "Found at index " << std::distance(nums.begin(), it) << std::endl;
        }
        ```
        Check the syntax.(3parameters);
        

Using `copy()` with Vectors

```c
The `copy()` function is part of the `<algorithm>` header and is used to copy elements from one range to another. While it's not directly applicable to vectors in the same way it is for arrays, you can use it in conjunction with `back_inserter` to append elements to a vector. Here's an example:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec1{1, 2, 3, 4};
    std::vector<int> vec2;

    // Use copy() to append elements from vec1 to vec2
    std::copy(vec1.begin(), vec1.end(), std::back_inserter(vec2));

    return 0;
}
```

### Using `insert()` with Vectors

The `insert()` function is a member function of `std::vector` that allows you to insert elements at a specific position in the vector. You can use it to concatenate two vectors or to insert elements at any position. Here's an example of using `insert()` to concatenate two vectors:

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> vec1{1, 2, 3};
    std::vector<int> vec2{4, 5, 6};

    // Concatenate vec2 to the end of vec1 using insert()
    vec1.insert(vec1.end(), vec2.begin(), vec2.end());

    return 0;
}
```

### Using `merge()` with Vectors

The `std::merge()` function is used to merge two sorted ranges into a single sorted range. This function requires that the input ranges are sorted. It's particularly useful when you need to combine two sorted vectors into a single sorted vector. Here's an example:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec1{1, 3, 5};
    std::vector<int> vec2{2, 4, 6};

    // Merge two sorted vectors into a single sorted vector
    std::vector<int> merged;
    std::merge(vec1.begin(), vec1.end(), vec2.begin(), vec2.end(), std::back_inserter(merged));

    return 0;
}
```

In this example, `vec1` and `vec2` are sorted, and `std::merge()` combines them into a single sorted vector `merged`.

Each of these methods serves different purposes: `copy()` is useful for appending elements to a vector, `insert()` allows for flexible insertion of elements at any position, and `merge()` efficiently combines two sorted ranges into a single sorted range.

# To convert a vector to a set and vice versa in C++

### Converting a Vector to a Set

### Method 1: Using `std::set` Constructor

```c
You can directly construct a set from a vector's range using the set's constructor that accepts two iterators.

```cpp
#include <iostream>
#include <vector>
#include <set>

using namespace std;

int main() {
    vector<int> vec = {1, 2, 3, 1, 1}; // Original vector
    set<int> s(vec.begin(), vec.end()); // Convert vector to set

    cout << "Set: ";
    for (int x : s) {
        cout << x << " ";
    }
    cout << endl;

    return 0;
}
```

#### Method 2: Using `std::set::insert`

Alternatively, you can insert elements from the vector into an empty set.

```cpp
#include <iostream>
#include <vector>
#include <set>

using namespace std;

int main() {
    vector<int> vec = {1, 2, 3, 1, 1}; // Original vector
    set<int> s; // Empty set

    for (int x : vec) {
        s.insert(x); // Insert each element into the set
    }

    cout << "Set: ";
    for (int x : s) {
        cout << x << " ";
    }
    cout << endl;

    return 0;
}
```

### Converting a Set to a Vector

#### Method 1: Using `std::vector::assign`

You can assign the elements of a set to a vector using the `assign` method.

```cpp
#include <iostream>
#include <vector>
#include <set>

using namespace std;

int main() {
    set<int> st = {1, 2, 3, 7, 9, 5}; // Original set
    vector<int> vc; // Empty vector

    vc.assign(st.begin(), st.end()); // Assign set elements to vector

    cout << "Vector after conversion: ";
    for (int i : vc) {
        cout << i << " ";
    }
    cout << endl;

    return 0;
}
```

#### Method 2: Using `std::vector::push_back`

Another approach is to iterate through the set and push each element into the vector.

```cpp
#include <iostream>
#include <vector>
#include <set>

using namespace std;

int main() {
    set<int> st = {1, 2, 3, 7, 9, 5}; // Original set
    vector<int> vc; // Empty vector

    for (int x : st) {
        vc.push_back(x); // Push each element into the vector
    }

    cout << "Vector after conversion: ";
    for (int i : vc) {
        cout << i << " ";
    }
    cout << endl;

    return 0;
}
```

Both methods for converting a set to a vector involve iterating over the set and either assigning its elements to a vector or pushing them back into the vector.

### sum of a vector

```c++
int sum = accumulate(nums.begin(), nums.end(), 0);
//Here 0 is the third argument. It is necessary to add this. 0 indicates to what value we should add the vector elements.if 1 then 1+element values.
```

# <span style="color: #e03e2d;">TYPE CONVERSION IN C++</span>

In C++, type conversions can be performed implicitly by the compiler or explicitly by the programmer using casting. Below are some common methods for type conversion in C++:

### <span style="color: #2dc26b;">You just use the implicit one.</span>

### Implicit Type Conversion

```c++
Implicit conversions are automatically performed by the compiler when converting a value from one type to another.

#### Example:

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 42;
    double d = i; // Implicit conversion from int to double
    cout << "i: " << i << ", d: " << d << endl; // Output: i: 42, d: 42.0
    return 0;
}
```

### Explicit Type Conversion (Casting)

Explicit conversions require the programmer to specify the conversion.

#### C-style Cast:

```cpp
#include <iostream>
using namespace std;

int main() {
    double d = 3.14;
    int i = (int)d; // C-style cast
    cout << "d: " << d << ", i: " << i << endl; // Output: d: 3.14, i: 3
    return 0;
}
```

## isdigit()

isdigit('6') will give true.

isdigit('s') will be false.

<span style="color: #000000;">we</span> <span style="color: #000000;">cannot</span> check with full numbers like 34. It is used for checking characters.

# <span style="color: #e03e2d;">BINARY TO DECIMAL AND VICE VERSA</span>

```C++
bitset<32> binarynumber(10);
//this will give o/p as : 00000000000000000000000000001010
32 means the number is converted to 32bit binary.
```

* * *

```c++
int decimal = stoi(binary, nullptr, 2);
 where binary is the  string="10011110"
 and 2 specifies the string is binary
```

We can do bitwise AND using one & as follows. also OR as 4|5.

```c++
#include <iostream>
using namespace std;

int main() {
    int a = 4; // binary: 0100
    int b = 5; // binary: 0101

    int result = a & b; // bitwise AND operation

    cout << "The result of " << a << " & " << b << " is: " << result << endl; // Output: 4

    // Detailed binary explanation
    cout << "Binary representation:" << endl;
    cout << "a = " << bitset<4>(a) << endl; // Output: 0100
    cout << "b = " << bitset<4>(b) << endl; // Output: 0101
    cout << "a & b = " << bitset<4>(result) << endl; // Output: 0100

    return 0;
}
```

&nbsp;

# <span style="color: #e03e2d;">BIT SHIFT OPERATOR</span>

### Bitwise Left Shift (`<<`)

The bitwise left shift (`<<`) operator moves the bits of a number to the left by a specified number of positions. Here's how it works:

- Syntax: `x << n`
    - `x` is the integer to be shifted.
    - `n` is the number of positions to shift `x` to the left.

Each left shift by `n` positions effectively multiplies `x` by `2^n` in terms of its numerical value. For example:

- `5 << 1` shifts `5` to the left by `1` position, resulting in `10` (`5` in binary `101` becomes `1010`).
- `7 << 2` shifts `7` to the left by `2` positions, resulting in `28` (`7` in binary `111` becomes `11100`).

### Bitwise Right Shift (`>>`)

The bitwise right shift (`>>`) operator moves the bits of a number to the right by a specified number of positions. Here's how it works:

- Syntax: `x >> n`
    - `x` is the integer to be shifted.
    - `n` is the number of positions to shift `x` to the right.

Each right shift by `n` positions effectively divides `x` by `2^n` in terms of its numerical value. For example:

- `10 >> 1` shifts `10` to the right by `1` position, resulting in `5` (`10` in binary `1010` becomes `101`).
- `28 >> 2` shifts `28` to the right by `2` positions, resulting in `7` (`28` in binary `11100` becomes `111`).

### Adding Zeros:

- When you perform a bitwise left shift (`<<`), you effectively add zeros to the right of the binary representation of the number.
- When you perform a bitwise right shift (`>>`), you effectively add zeros to the left of the binary representation of the number.

&nbsp;
### pair
The `pair` class in the C++ Standard Template Library (STL) is a simple container that stores two heterogeneous objects as a single unit. The `pair` class is defined in the `<utility>` header. It is particularly useful for creating complex data structures, such as maps, where each element is a key-value pair.

### Syntax  
```cpp  
#include <utility> // Required for pair  
pair<Type1, Type2> pairName (value1, value2);  
```

### Example  
Here's a basic example to illustrate how to use `pair` in STL:

```cpp  
#include <iostream>  
#include <utility> // Required for pair  
#include <string>

using namespace std;

int main() {  
// Creating a pair of an integer and a string  
pair<int, string> student(1, "John Doe");

// Accessing elements of the pair  
cout << "ID: " << student.first << ", Name: " << student.second << endl;

// Creating another pair using make_pair  
pair<int, string> student2 = make_pair(2, "Jane Smith");

// Accessing elements of the pair  
cout << "ID: " << student2.first << ", Name: " << student2.second << endl;

return 0;  
}  
```

### Explanation:  
1. **Including the Header**: The `<utility>` header is required to use the `pair` class.  
2. **Creating a Pair**: The `pair` object `student` is created with an integer (1) and a string ("John Doe").  
3. **Accessing Elements**: The elements of the pair can be accessed using the `.first` and `.second` members.  
4. **Using `make_pair`**: The `make_pair` function is a convenient way to create a `pair` without specifying the types explicitly.

### Common Use Cases  
1. **Returning Multiple Values from a Function**: A function can return a `pair` to return two values.  
2. **Storing Key-Value Pairs**: In associative containers like `map` and `unordered_map`, `pair` is used to store key-value pairs.  
3. **Complex Data Structures**: When you need to associate two different types of values together.

### Example with `map`  
Here’s an example of using `pair` with `map`:

```cpp  
#include <iostream>  
#include <map>  
#include <string>

using namespace std;

int main() {  
// Creating a map of int and string pairs  
map<int, string> students;

// Inserting pairs into the map  
students.insert(pair<int, string>(1, "John Doe"));  
students.insert(make_pair(2, "Jane Smith"));

// Accessing elements  
for (const auto& student : students) {  
cout << "ID: " << student.first << ", Name: " << student.second << endl;  
}

return 0;  
}  
```

### Explanation:  
1. **Creating a `map`**: The `map` is a container that stores `pair` elements, where each `pair` consists of a key and a value.  
2. **Inserting Pairs**: Pairs are inserted into the `map` using `insert` and `make_pair`.  
3. **Iterating Over the Map**: The `map` is iterated using a range-based for loop to access each `pair`.

This demonstrates the versatility and utility of the `pair` class in C++.


### DFS traversal of a graph
```cpp
#include <iostream>
#include <vector>

using namespace std;

void dfs(int node, vector<vector<int>>& graph, vector<bool>& visited) {
    visited[node] = true;
    cout << node << " ";

    for (int neighbor : graph[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor, graph, visited);
        }
    }
}

int main() {
    // Example graph represented as an adjacency list
    vector<vector<int>> graph = {
        {1, 2},     // Neighbors of node 0
        {0, 3, 4},  // Neighbors of node 1
        {0, 4},     // Neighbors of node 2
        {1, 4, 5},  // Neighbors of node 3
        {1, 2, 3},  // Neighbors of node 4
        {3}         // Neighbors of node 5
    };

    int numNodes = graph.size();
    vector<bool> visited(numNodes, false);

    // Start DFS from node 0
    cout << "DFS traversal starting from node 0: ";
    dfs(0, graph, visited);
    cout << endl;

    return 0;
}
```
### BFS traversal
```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <unordered_set>

using namespace std;

class Graph {
public:
    Graph(int vertices);
    void addEdge(int u, int v);
    void BFS(int start);

private:
    vector<vector<int>> adjList;
    int numVertices;
};

Graph::Graph(int vertices) : numVertices(vertices) {
    adjList.resize(vertices);
}

void Graph::addEdge(int u, int v) {
    adjList[u].push_back(v);
    adjList[v].push_back(u); // If the graph is undirected
}

void Graph::BFS(int start) {
    vector<bool> visited(numVertices, false);
    queue<int> q;

    visited[start] = true;
    q.push(start);

    while (!q.empty()) {
        int node = q.front();
        q.pop();
        cout << node << " ";

        for (int neighbor : adjList[node]) {
            if (!visited[neighbor]) {
                visited[neighbor] = true;
                q.push(neighbor);
            }
        }
    }
}

int main() {
    Graph g(6);

    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 3);
    g.addEdge(1, 4);
    g.addEdge(2, 5);

    cout << "BFS starting from node 0: ";
    g.BFS(0);
    cout << endl;

    return 0;
}
```
#### in C++
```cpp
#include <iostream>
#include <queue>
#include <vector>

using namespace std;

void BFS(vector<vector<int>>& adjMatrix, int start) {
    int n = adjMatrix.size();
    vector<bool> visited(n, false);
    queue<int> q;

    q.push(start);
    visited[start] = true;

    cout << "BFS Traversal: ";

    while (!q.empty()) {
        int node = q.front();
        q.pop();
        cout << node << " ";

        for (int i = 0; i < n; i++) {
            if (adjMatrix[node][i] == 1 && !visited[i]) {
                q.push(i);
                visited[i] = true;
            }
        }
    }
    cout << endl;
}

int main() {
    int n, start;
    cout << "Enter number of nodes: ";
    cin >> n;

    vector<vector<int>> adjMatrix(n, vector<int>(n));
    cout << "Enter Adjacency matrix for the graph: " << endl;
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            cin >> adjMatrix[i][j];
        }
    }

    cout << "Enter starting node (0-" << (n - 1) << "): ";
    cin >> start;

    BFS(adjMatrix, start);

    return 0;
}
```
