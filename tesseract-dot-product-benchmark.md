# Comparison of execution time with different dot product implementations

Data was provided by @stweil.

* time lstm_squashed_test
* time DOTPRODUCT=accelerate lstm_squashed_test
* time DOTPRODUCT=generic lstm_squashed_test
* time DOTPRODUCT=native lstm_squashed_test

https://github.com/tesseract-ocr/tesseract/tree/master/src/arch

| System | OS | Compiler | MT/ST | f64/f32 | Dot Product | Sec | Norm |
| -- | -- | -- | -- | -- | -- | -- | -- |
| Apple M1 | macOS | clang | MT | 64 | DP Accelerate | 33 s | 1.10 |
| Apple M1 | macOS | clang | MT | 64 | DP Native  | 30 s | 1.00 |
| Apple M1 | macOS | clang | MT | 64 | DP Generic | 64 s | 2.13 |
|   |   |   |   |   |   |   |   |
| Apple M1 | macOS | clang | MT | 32 | DP Accelerate | 23 s | 1.05 |
| Apple M1 | macOS | clang | MT | 32 | DP Native | 22 s | 1.00 |
|   |   |   |   |   |   |   |   |
| Macbook intel Core i5 1.4 MHz | macOS | clang | ST | 64 | DP default) | 60 s | 1.00 |
| Macbook intel Core i5 1.4 MHz | macOS | clang | ST | 64 | DP Accelerate | 78 s | 1.3 |
| Macbook intel Core i5 1.4 MHz | macOS | clang | ST | 64 | DP Native | 65 s | 1.08 |
| Macbook intel Core i5 1.4 MHz | macOS | clang | ST | 64 | DP Generic | 108 s | 1.80 |
|   |   |   |   |   |   |   |   |
| Macbook intel Core i5 1.4 MHz | macOS | clang | ST | 32 | DP (default) | 49 s | (0.82) |
|   |   |   |   |   |   |   |   |
| intel Xeon CPU E5-2620 v4 @ 1.10GHz | Linux | g++ 8.3.0 | MT | 64 | DP (default) | 53 s | 1.0 |
| intel Xeon CPU E5-2620 v4 @ 1.10GHz | Linux | g++ 8.3.0 | MT | 64 | DP Native  | 139 s | 2.62
| intel Xeon CPU E5-2620 v4 @ 1.10GHz | Linux | g++ 8.3.0 | MT | 64 | DP Generic | 105 s | 1.98 |
|   |   |   |   |   |   |   |   |
| intel Xeon CPU E5-2620 v4 @ 1.10GHz | Linux | clang 7 | MT | 64 | DP (default) | 47 s | 1. |
| intel Xeon CPU E5-2620 v4 @ 1.10GHz | Linux | clang 7 | MT | 64 | DP Native  | 55 s | 1. |
| intel Xeon CPU E5-2620 v4 @ 1.10GHz | Linux | clang 7 | MT | 64 | DP Generic | 99 s | 1. |
|   |   |   |   |   |   |   |   |
| AMD EPYC 7502 | Linux | g++ 10.1.1 | ST | 64 | DP default) | 36 s | 1. |
| AMD EPYC 7502 | Linux | g++ 10.1.1 | ST | 64 | DP Native | 87 s | 1. |
| AMD EPYC 7502 | Linux | g++ 10.1.1 | ST | 64 | DP Generic | 91 s | 1. |
|   |   |   |   |   |   |   |   |
| AMD EPYC 7502 | Linux | g++ 10.1.1 | ST | 32 | DP (default) | 28 s | 1. |
|   |   |   |   |   |   |   |   |
| AMD EPYC 7502 | Linux | clang 11 | ST | 64 | DP (default) | 32 s | 1. |
| AMD EPYC 7502 | Linux | clang 11 | ST | 64 | DP Native | 37 s | 1. |
| AMD EPYC 7502 | Linux | clang 11 | ST | 64 | DP Generic | 76 s | 1. |
|   |   |   |   |   |   |   |   |
| NVIDIA Jetson Xavier | Linux | g++ 9.3.0 | ST | 64 | DP (default) | 113 s | 1. |
| NVIDIA Jetson Xavier | Linux | g++ 9.3.0 | ST | 64 | DP Native | 179 s | 1. |
| NVIDIA Jetson Xavier | Linux | g++ 9.3.0 | ST | 64 | DP Generic | 180 s | 1. |
|   |   |   |   |   |   |   |   |
| NVIDIA Jetson Xavier | Linux | g++ 9.3.0 | ST | 32 | DP (default) | 97 s | 1. |
| NVIDIA Jetson Xavier | Linux | g++ 9.3.0 | ST | 32 | DP Native | 96 s | 1. |
|   |   |   |   |   |   |   |   |
| NVIDIA Jetson Xavier | Linux | clang 11 | ST | 64 | DP (default) | 97 s | 1. |
| NVIDIA Jetson Xavier | Linux | clang 11 | ST | 64 | DP Native | 104 s | 1. |
| NVIDIA Jetson Xavier | Linux | clang 11 | ST | 64 | DP Generic | 185 s | 1. |
|   |   |   |   |   |   |   |   |
| NVIDIA Jetson Xavier | Linux | clang 11 | ST | 32 | DP (default) | 86 s | 1. |
| NVIDIA Jetson Xavier | Linux | clang 11 | ST | 32 | DP Native | 83 s | 1. |
|   |   |   |   |   |   |   |   |
| Power8 3425 MHz | Linux | g++ 10.1.1 | ST | 64 | DP  Native | 130 s | 1.00 |
| Power8 3425 MHz | Linux | g++ 10.1.1 | ST | 64 | DP  Generic | 179 s | 1.38 |
