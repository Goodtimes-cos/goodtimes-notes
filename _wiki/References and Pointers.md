---
date: 2024-06-25
tags: computers compsci
---
# References and Pointers
## References
A reference variable is an alias to an existing variable. All changes
to the target variable will similarly change the reference variable.

When not used in a declaration, references are used to access the
memory address of a variable.

### Usage in C++
```
#include <iostream>
#include <string>

int main () {
	int exam_grade = 85;
	int& score = exam_grade;

	score += 7

	std::cout << exam_grade << std::endl;
	std::cout << score << std::endl;

	std::string message = "Hello World!";
	std::cout << message << std::endl;
	std::cout << &message << std::endl;

	return 0;
}
```

## Pointers
A pointer in C++ is a variable that stores (points to) a memory address.
To access the value of the memory address assigned to a pointer, we
may deference it.

### Usage in C++
```
#include <iostream>
#include <string>

int main() {

	std::string name = "John";
	std::string* ptr = nullptr;

	ptr = &name;

	std::cout << ptr << '\n';
	std::cout << *ptr << '\n';

	*ptr = "Robin";

	std::cout << *ptr << '\n';
	std::cout << name << '\n';
	
	return 0;
}
```