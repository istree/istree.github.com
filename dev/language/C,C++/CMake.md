---
title: CMake
---
## 개요

make 파일을 각 OS에 맞게 생성해주는 명령어 도구이다. CLion 빌드시 기반으로 사용된다.

확장자는 따로 없고 그냥 텍스트파일로 작성하면 된다.

## 빠른 예제

common 라이브러리를  각각 링크하는 Apple 프로그램과 Banana 프로그램이 있는 경우

```cmake
cmake_minimum_required(VERSION 3.7)
project(examples)

set(CMAKE_CXX_STANDARD 11)

# common library
file(GLOB FILE_COMMON "common/*.h" "common/*.cpp")
include_directories(common)
add_library(common ${FILE_COMMON})

# apple exe
file(GLOB FILE_APPLE "Apple/*.h" "Apple/*.cpp")
add_executable(Apple ${FILE_APPLE})

# banana exe
file(GLOB FILE_BANANA "Banana/*.h" "Banana/*.cpp")
add_executable(Banana ${FILE_BANANA})

# link
target_link_libraries(Apple common)
target_link_libraries(Banana common)
```

## 여러 파일 지정

flie 명령어는 와일드카드로 한번에 특정 확장자를 지정할 수 있다.
```cmake
file(GLOB FILE_APPLE "Apple/*.h" "Apple/*.cpp")
```

set 명령으로 특정 파일을 한개씩 지정할 수도 있다.
```cmake
set(FILE_APPLE "Apple/apple.h" "Apple/apple.cpp" "Apple/pineapple.h" "Apple/pineapple.cpp")
```