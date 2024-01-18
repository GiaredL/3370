# Circular Buffer Implementation
Overview:
Implement a Circular Buffer class in C++ that handles dynamic memory allocation for character elements.

## Class Structure:

#include <string>
using std::string;

class CircBuf {
private:
    const size_t CHUNK { 8 };
    // Insert your data and private functions here.

public:
    // Constructor
    CircBuf(size_t reserve = 0); // Number of elements to reserve space for initially

    // Destructor
    ~CircBuf();

    // Public Member Functions
    size_t size();
    size_t capacity();
    void insert(char);
    void insert(const char*, size_t sz);
    void insert(const string&);
    char get();
    string get(size_t);
    string flush(); // Returns a string with all characters and shrinks the buffer to zero.
    string examine(); // Returns a string representing the contents of the buffer.
    void shrink(); // Reduces the unused space in the buffer.
};


# Implementation Details:
## Circular Buffer Structure:

-Utilize a dynamic (heap) array for storing characters.
-Maintain integer indexes (or pointers) for the head and tail of the data in use.
-Wrap around to the beginning when either index reaches the end of the buffer.
-Dynamic Array Growth:

-When adding more characters than the buffer has room for, dynamically grow the internal array.
-Allocate a new array that is one CHUNK larger than the previous one.
-Copy data from the old array into the new one while preserving the order.
-Clean up to avoid memory leaks.
-Size and Capacity:

-Track the number of elements in the buffer (size).
-Determine the maximum number of elements without growing the buffer (capacity).
-Constructor:

-Takes an argument specifying the number of elements to reserve space for initially.
-Insert and Get Functions:

-Insert single characters, multiple characters, and strings.
-Retrieve single characters or a specified number of characters as a string.
-Examine Function:

-Verify correctness with a function named examine().
-Returns a string representing the contents of the buffer, enclosed in square brackets.
-Unused elements represented by '-'.
-Shrink Function:

-Implement a function to reduce the size of the buffer.

#Submission Instructions:

-Implement the CircBuf class in a file called CircBuf.cpp.
-Submit CircBuf.h and CircBuf.cpp.
-Include a screenshot of the program output.
-Compile CircBuf.cpp with main.cpp and test.h for testing (51 test cases in main.cpp).

##Professional Tip:

-Write clear and well-documented code for better readability.
-Provide comments detailing your thought process and any challenges overcome.

##Additional Notes:
-Do not turn in the entire MS Visual Studio project folder.
-The grader may run additional test cases against your program.

#Grading:
-Pass all 51 test cases in main.cpp for full credit.
-Grader reserves the right to run additional test cases.
-Include a comment block summarizing your learning and any challenges faced in the source code. (5 points out of 100)
