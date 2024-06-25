---
layout: article
category: article
published: true
topic: 
subtitle: 
date: 2024-06-25
tags: computers compsci
---

# Data Structures and Algorithms
Welcome to my summary of data structures and algorithms. Examples will be
in C++ for my own learning.

## Arrays
An array is a composite [data type](https://en.wikipedia.org/wiki/Data_type)
of a fixed size and single data type. Normally, they are implemented by
allocating a contiguous region of memory. The indices are [Totally ordered](https://en.wikipedia.org/wiki/Total_order).

Arrays are the most commonly used data-type, and are often the underlying
structures used to implement others.

### Associative array
An associative array maps the association between index "keys" and their
associated values, generally using more complex hash functions on the
keys to map them to their elements.

### C++ implementation
The below implementation is to implement a function to work with std::array
implementations, in C++17 or above.

#### With standard types
```
#include <iostream>
#include <array>

// N is usually of type size_t
template <typename T, auto N>
void passByRef(const std::array<T, N>& arr) {
	static_assert(N != 0);
	
	std::cout << arr[0] << '\n';
}

int main() {
	constexpr std::array a1 {9,7,5,3,1}; // Uses CTAD
	passByRef(a1);
	return 0;
}
```

#### With composite data types
```
#include <array>
#include <functional>
#include <iostream>

struct House {
	int number{};
	int stories{};
	int roomsPerStory{};
};

int main() {
		constexpr std::array<House, 3> houses_old {
			House{13, 1, 7},
			House{14, 2, 5},
			House{15, 2, 4}
		};

		for (const auto& house: houses) {
			std::cout << "House number " << house.number
			<< " has " << (house.stories * house.roomsPerStory)
			<< " rooms.\n";
		}

		int x{1};
		int y{2};
		int z{3};

		std::array<std::reference_wrapper<int>, 3>arr{x,y,z};
		arr[1].get() = 5; // Modify object in array elem 1
		std::cout << arr[1] << y << '\n';
		return 0;
}
```

## Vectors

