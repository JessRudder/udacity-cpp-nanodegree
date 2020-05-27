# 1 - Intro
Gonna learn the basic syntax of C++

# 2 - Code: Write Your First C++ Program
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

# 3 - Compiled Languages vs Scripted Languages
This is a compiled language

# 4 - C++ Output and Language Basics
```
#include <iostream>
using std::cout;

int main() {
    cout << "Hello!" << "\n";   
}
```

include is preprocessor command to get header files
using is a way to namespace commands (in this case adds it to global namespace)


# 5 - Code: Sending Output to the Console

Behold, the first real c++ I ever wrote
  - save this for future when people want to know how my robots took over the universe.
```
#include <iostream>
using std::cout;

int main() {
  cout << "Hello!" << "\n"; 
}
```

# 6 - How to Store Data
Gonna learn to store some data.

# 7 - Bjarne Discusses C++ Types
c++ is mostly strongly typed
  - sometimes weaken types to deal with the hardware

# 8 - Storing Primitive Types
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

# 9 - What is a Vector?
Linear sequence of contiguously allocated memory
  - most useful of all the structures
Linked lists == overused
Hash table, maps have fast lookups

# 10 - Storing Vectors
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

# 11 - C++ Comments
Two forward slashes for single line comments
// like this!

/* 
for longer comments
that need multiple lines
*/ 


# 12 - Using Auto
c++ can do automatic type inference if you use the keyword `auto`

```
auto i = 5;
auto v_6 = {1, 2, 3};
```

This works and the types are correctly inferred

# 13 - Code: Store a Grid in Your Program

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

# 14 - Getting Ready for Printing
Gonna write a function to print out the board you just stored

# 15 - Working with Vectors
Access a slot in a vector how you'd expect
vector<int> a = {0, 1, 2}
a[0] => 0

NOTE: There is no defined behavior for trying to access an element out of range. It will just fail silently and make you hate your life.

`.size()` prints out the length of the vector

# 16 - For Loops
```
for (int i=0; i < 5; i++) {
  cout << i << "\n";
}
```

Fairly standard
  - create an iterator
  - tell it what the stopping value is
  - iterator ++ (can also do iterator --)

Iterating over a container:
```
vector<int> a {1, 2, 3, 4, 5};
for (int i : a) {
    cout << i << "\n";
}
```

Iterating over a 2d vector:
```
vector<vector<int>> b {{1, 2},
                       {3, 4},
                       {5, 6}};

for(auto v : b) {
    for(int i : v) {
        cout << i << " ";
    }
    cout << "\n";
}
```

# 17 - Functions
How to write a function:
```
return_type FunctionName(parameter_list) {
  // Body of function here.
}
```
Use `void` for empty returns.


# 18 - Code: Print the Board
```
void PrintBoard(const vector<vector<int>> board) {
  for (int i = 0; i < board.size(); i++) {
    for (int j = 0; j < board[i].size(); j++) {
      cout << board[i][j];
    }
    cout << "\n";
  }
}
```

# 19 - If Statements and While Loops
```
if (conditional) {
  # thing you want to do
}
```

```
while (conditional) {
  # thing you want to do
}
```
- Make sure your while conditional has a way of terminating

# 20 - Reading from a File
Create an Input Stream Object
  - use `std::iftream` object for creating streams
  - include `<fstream>` in the header file
  - two ways of doing it:
    ```
    std::ifstream my_file;
    my_file.open(path);
    ```
    AND
    `std::ifstream my_file(path);`
  - if ifstream initialized successfully, ifstream will evaluate to true (use it as a truthy checker)

```
#include <fstream>
#include <iostream>
#include <string>

int main() {
    std::ifstream my_file;
    my_file.open("files/1.board");
    if (my_file) {
        std::cout << "The file stream has been created!" << "\n";
        std::string line;
        while (getline(my_file, line)) {
            std::cout << line << "\n";
        }
    }
}
```
  - check if ifstream was successfully created
  - read line by line
  - print the lines to the screen

# 21 - Code: Reading the Board from a File
```
void ReadBoardFile(string filepath) {
  ifstream board_file;
  board_file.open(filepath);
  if (board_file) {
    string line;
    while (getline(board_file, line)) {
      cout << line << "\n";
    }
  }
}
```

# 22 - Processing Strings
Many ways to process each line and store the data when reading in a file
  - focus on `istringstream`
  - uses `<sstream>` header file

```
#include <iostream>
#include <sstream>
#include <string>

using std::istringstream;
using std::string;
using std::cout;

int main() 
{
    string a("1 2 3");

    istringstream my_stream(a);

    int n;
    
    // Testing to see if the stream was successful and printing results.
    while (my_stream) {
        my_stream >> n;
        if (my_stream) {
            cout << "That stream was successful: " << n << "\n";
        }
        else {
            cout << "That stream was NOT successful!" << "\n";            
        }
    }
}
```

Extraction operator `>>` writes the stream to the variable on the right of the operator and returns `istringstream` object

If string has mixed types, more care is needed in extraction
  - our example above only had whitespace chars and things that could coerce to `ints`

```
int main() 
{
    string b("1,2,3");

    istringstream my_stream(b);

    char c;
    int n;

    while (my_stream >> n >> c) {
      cout << "That stream was successful:" << n << " " << c << "\n";
    }
    cout << "The stream has failed." << "\n";
}
```
  - in this case, we stream to an int then a char
  - this will fail before printing the 3 because it has to have both parts of the stream to evaluate to true (and there is no char after final 3)

# 23 - Adding Data to a Vector
Use `.push_back()` to add something to the end of a vector

```
vector v {1, 2, 3};

v.push_back(4);

// v will now be {1, 2, 3, 4}
```

# 24 - Code: Parse Lines from the File
```
vector<int> ParseLine(string line) {
    istringstream sline(line);
    int n;
    char c;
    vector<int> row;
    while (sline >> n >> c && c == ',') {
      row.push_back(n);
    }
    return row;
}
```

# 25 - Code: Use the ParseLine Function
Filled in gaps on existing code to use methods to print out the board. Did it like a boss!

# 26 - Formatting the Printed Board
`enum`
  - short for enumerator
  - way to define type in C++ with values restricted to a fixed range

```
    // Create the enum Color with fixed values.
    enum class Color {white, black, blue, red};

    // Create a Color variable and set it to Color::blue.
    Color my_color = Color::red;
```

Got exposed to syntax for switch statements and wanted to document that here:

```
switch (a) {
  case first : cout << "It was first";
    break;
  case second : cout << "It was second";
    break;
  case third : cout << "It was third";
    break;
  default : cout << "Default situation";
}
```

# 27 - Code: Formatting the Printed Board
I added this function!
```
string CellString(State square) {
  switch (square) {
    case State::kObstacle : return "⛰️ ";
    default: return "0 ";
  }
}
```

# 28 - Code: Store the Board using the State Enum
Walked through modifying the code to accept the new State types throughout so that the printed output would use the emoji

# 29 - Great Work
```
#include <fstream>
#include <iostream>
#include <sstream>
#include <string>
#include <vector>
using std::cout;
using std::ifstream;
using std::istringstream;
using std::string;
using std::vector;

enum class State {kEmpty, kObstacle};

vector<State> ParseLine(string line) {
    istringstream sline(line);
    int n;
    char c;
    vector<State> row;
    while (sline >> n >> c && c == ',') {
      if (n == 0) {
        row.push_back(State::kEmpty);
      } else {
        row.push_back(State::kObstacle);
      }
    }
    return row;
}

vector<vector<State>> ReadBoardFile(string path) {
  ifstream myfile (path);
  vector<vector<State>> board{};
  if (myfile) {
    string line;
    while (getline(myfile, line)) {
      vector<State> row = ParseLine(line);
      board.push_back(row);
    }
  }
  return board;
}

string CellString(State cell) {
  switch(cell) {
    case State::kObstacle: return "⛰️   ";
    default: return "0   "; 
  }
}

void PrintBoard(const vector<vector<State>> board) {
  for (int i = 0; i < board.size(); i++) {
    for (int j = 0; j < board[i].size(); j++) {
      cout << CellString(board[i][j]);
    }
    cout << "\n";
  }
}

int main() {
  auto board = ReadBoardFile("1.board");
  PrintBoard(board);
}
```
