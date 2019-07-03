# 1 - Intro
Gonna learn the basic syntax of C++

# 2 - Motion Planning
Have to devise a plan on getting from point A to point B

# 3 - Quiz: Maze
7 steps to get from a to b in shortest path

# 4 - Quiz: Maze 2
11 steps to get from a to b in shortest path

# 5 - Coding the Shortest Path Algorithm
Give grid cell names


   0   1   2   3

0

1

2

3

Check spaces around you and see if they're open
Start [0,0]
Going to search the ones around it
  - expand the one with the smallest possible g-value
  - goal value (?)
Then you might have to recurse


# 6 - Code: Write Your First C++ Program
Every program has a `main` function which executes when the program runs
  - everything else is run directly or indirectly from `main`
  - should always return an integer which indicates if the program exited successfully

Smalles c++ program:
```
int main() {
}
```
Compile with `g++ your_file.cpp`
Run with `./a.out`

# 7 - Compiled Languages vs Scripted Languages
This is a compiled language

# 8 - C++ Output and Language Basics
```
#include <iostream>
using std::cout;

int main() {
    cout << "Hello!" << "\n";   
}
```

include is preprocessor command to get header files
using is a way to namespace commands (in this case adds it to global namespace)


# 9 - Code: Sending Output to the Console

Behold, the first real c++ I ever wrote
  - save this for future when people want to know how my robots took over the universe.
```
#include <iostream>
using std::cout;

int main() {
  cout << "Hello!" << "\n"; 
}
```

# 10 - How to Store Data
Gonna learn to store some data.

# 11 - Bjarne Discusses C++ Types
c++ is mostly strongly typed
  - sometimes weaken types to deal with the hardware

# 12 - Storing Primitive Types
Things like `int`s, `string`s, `float`s
If you try to dealre a var twice in same function you'll see an error

```
    // Declaring and initializing an int variable.
    int a = 9;
    
    // Declaring a string variable without initializing right away.
    std::string b;
    
    // Initializing the string b.
    b = "Here is a string";
```

# 13 - What is a Vector?
Linear sequence of contiguously allocated memory
  - most useful of all the structures
Linked lists == overused
Hash table, maps have fast lookups

# 14 - Storing Vectors
```
  // Three ways of declaring and initializing vectors.
  vector<int> v_1{0, 1, 2};
  vector<int> v_2 = {3, 4, 5};
  vector<int> v_3;
  v_3 = {6};
```

Vectors can be 2-dimensional
```
vector<vector<int>> v {{1,2}, {3,4}};
```

# 15 - C++ Comments
Two forward slashes for single line comments
// like this!

/* 
for longer comments
that need multiple lines
*/ 


# 16 - Using Auto
c++ can do automatic type inference if you use the keyword `auto`

```
auto i = 5;
auto v_6 = {1, 2, 3};
```

This works and the types are correctly inferred

# 17 - Code: Store a Grid in Your Program

```
#include <iostream>
#include <vector>
using std::cout;
using std::vector;


int main() {
  vector<vector<int>> board = {{0, 1, 0, 0, 0, 0},
{0, 1, 0, 0, 0, 0},
{0, 1, 0, 0, 0, 0},
{0, 1, 0, 0, 0, 0},
{0, 0, 0, 0, 1, 0}};
  
  cout << "It compiled!" << "\n";
}
```

# 18 - Getting Ready for Printing
Gonna write a function to print out the board you just stored

# 19 - Working with Vectors
Access a slot in a vector how you'd expect
vector<int> a = {0, 1, 2}
a[0] => 0

NOTE: There is no defined behavior for trying to access an element out of range. It will just fail silently and make you hate your life.

`.size()` prints out the length of the vector

# 20 - For Loops


# 21 - Functions


# 22 - Code: Print the Board


# 23 - If Statements and While Loops


# 24 - Reading from a File


# 25 - Code: Reading the Board from a File


# 26 - Processing Strings


# 27 - Adding Data to a Vector


# 28 - Code: Parse Lines from the File


# 29 - Code: Use the ParseLine Function


# 30 - Formatting the Printed Board


# 31 - Code: Formatting the Printed Board


# 32 - Code: Store the Board using the State Enum


# 33 - Great Work

