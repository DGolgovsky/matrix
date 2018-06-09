# matrix
Homework 06 task. [OTUS C++]

[![Build Status](https://travis-ci.org/DGolgovsky/matrix.svg?branch=master)](https://travis-ci.org/DGolgovsky/matrix)
[![Code Health](https://landscape.io/github/DGolgovsky/matrix/master/landscape.svg?style=flat)](https://landscape.io/github/DGolgovsky/matrix/master)
[ ![Download](https://api.bintray.com/packages/dgolgovsky/otus-cpp/matrix/images/download.svg) ](https://bintray.com/dgolgovsky/otus-cpp/matrix/_latestVersion)

**Task description**

Design a 2-dimensional discharged infinite matrix filled with default values.
The matrix kept only by filled elements, those whose meanings were at least once assigned. Assignment The cell in the default value frees the cell.

It is necessary to be able to answer the question - how many cells are really occupied?
It is necessary to be able to pass through all occupied cells.
Order does not have values. The position of the cell and its value are returned.
When reading an element from a free cell, default.

**Example**
```
Matrix <int, -1> matirx; // int -1
assert (Matrix.size () == 0);

auto a = Matrix [0] [0];
assert (a == -1);
assert (Matrix.size () == 0);

Matrix [100] [100] = 314;
assert (Matrix [100] [100] == 314);
assert (Matrix.size () == 1);

// 100100314
for (auto c: Matrix)
{
	int x;
	int y;
	int v;
	std::tie (x, y, v) = c;
	std::cout << x << y << v << std::endl;
}
```

When run the program, you must create a matrix with an empty value 0, fill the main diagonal of the matrix (from [0,0] to [9,9]) with the values ​​from 0 to 9.

Secondary diagonal (from [0,9] to [9,0]) values ​​from 9 to 0.

It is necessary to deduce a fragment of the matrix from [1,1] to [8,8]. Between the tablets space. Each row of the matrix on the new console line.

Output the number of occupied cells. Output all occupied cells along with their positions.

Detailed description on the [gh-pages](https://dgolgovsky.github.io/matrix/)

**Dockerfile**

```
FROM ubuntu:trusty
#### Bintray (by JFrog) 
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 379CE192D401AB61
#### Dmitry Golgovsky (Packages sign) 
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys D5CEB8D4D5185900
#### toolchain repo key
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 1E9377A2BA9EF27F
RUN echo "deb http://dl.bintray.com/dgolgovsky/otus-cpp trusty main" | sudo tee -a /etc/apt/sources.list
RUN echo "deb http://ppa.launchpad.net/ubuntu-toolchain-r/test/ubuntu trusty main" | sudo tee -a /etc/apt/sources.list
RUN apt update
RUN apt install -y libstdc++6 matrix
```

**OTUS**

OTUS C++ online [course](https://otus.ru/lessons/razrabotchik-c++/) studying repository.

**About the course**

Being one of the most popular programming languages, C++ is widely used for software development. Scope of usage includes the creation of operating systems, a variety of applications, device drivers, applications for embedded systems, high-performance servers, and entertainment applications (games).
In the course "C++ Developer" will be considered as introductory concepts, such as automation tools, STL, innovations of `11` and `14` standards; and more complex: asynchronous programming, design patterns, distributed high-availability services architectures.
