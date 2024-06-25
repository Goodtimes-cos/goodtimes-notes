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
A summary of Data Structures and Algorithms in C++. For more detail,
it's probably best to either find another tutorial, or look at my implemetations
of [RosettaCode](https://github.com/Goodtimes-cos/DSA/tree/main/C%2B%2B/ProblemSets/RosettaCode) problems.

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
implementations, in C++17 or above. Note that while C-style arrays
can be used in C++, it's recommend to use std::array implementations unless
the task is rudimentary.

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
		// See alternative method of doing this, artifact
		of aggregate init
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
A vector in C++ is essentially a dynamic array. It too stores elements linearly
in memory. Crucially, they can change in size, unlike arrays.

### C++ implementation

```
#include <numeric>
#include <vector>
#include <iostream>

// Paras could also be const T& arr for allowing any object.
template <typename T>
void passByRef(const std::vector<T>& arr) {
	std::cout << arr[0] << '\n';
}

int main() {
	std::vector<int> empty{};
	std::vector<int> primes{2,3,5,7,11};
	std::vector<int> data(10);

	int x,y,z;
	std::cout << "Enter 3 integers: ";
	std::cin >> x >> y >> z;
	std::cout << "The sum is: " << x+y+z;
	std::cout << "\nThe product is: " << x*y*z << std::endl;

	std::vector<int> values{x, y, z};
	std::cout << "The sum is: " << std::reduce(
	values.begin(), 
	values.end()
	);

	// Alternative ways of multiplying together
	std::cout << "\nThe product is: " << std::accumulate(
		std::begin(values), std::end(values),
		1.0, std::multiplies<int>()) << std::endl; // C++98

	int multi = 1;
	for (const auto& e: values)
		multi *= e;

	std::cout << multi << std::endl;

	passByRef(primes);

	return 0;
}
```

### Usage note
Usually, it's best to use std::array. However, if you need dynamic arrays,
and memory constraints aren't severe, using std::vector is a great choice.
Furthermore, using std::vector guarantees it's heap-allocated, which can
be useful in certain contexts.

## Hash tables
A Hash Table is a data structure which organises data using hash functions
in order to support quick insertion and search.

There are two kinds of hash tables:
- The hash set, where no values may repeat,
- A hash hap, where we store (key, value) pairs.

The key idea of a Hash Table is to use a hash function to map
keys to buckets. We decide which bucket the key should be assigned
using a hash function.

Ideally, a perfect hash function will be a one-to-one mapping between
key and bucket, but this is often not possible. So, we must trade off
the number of buckets to the capacity of a bucket.