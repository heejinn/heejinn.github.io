---
title:  "[C++] C++을 공부하기 전에..." 
excerpt: "C++을 공부하기 전에 알면 좋은 간단한 내용들을 정리하였습니다."

categories:
  -  cpp
tags:
  - [C++, Programming]

toc: true
toc_label: 목차
toc_sticky: true

date: 2023-01-17
last_modified_at: 2023-01-28
---

컴퓨터의 **프로그램**은 특정 작업을 수행하기 위한 **명령어의 집합**이며 이러한 프로그램을 만드는 과정을 **프로그래밍**이라 한다.  

**프로그래머**는 명령어들이 적힌 하나 이상의 텍스트 파일, 즉 **코드**를 작성하여 프로그램을 만들고 이렇게 만들어진 프로그램은 컴퓨터의 메모리에 로드되어 실행된다.

## 기계어 (Machine Language)
컴퓨터의 CPU가 이해할 수 있는 명령어로 **Binary Digit(0과 1)**으로 구성되어 있다. 기계어로 프로그램을 작성하는 것은 어렵고 시간과 노력이 많이 들어갔으며, 이식성이 낮아 CPU의 종류가 바뀌면 프로그램을 다시 작성해야 하는 번거로움이 있었다.

예) ```10110000 01100001```

## 어셈블리어 (Assembly Language)
기계어의 문제점을 해결하기 위해 만들어진 언어이며, 기계어보다 훨씬 이해하고 작성하기 쉽지만, CPU는 어셈블리어를 바로 이해할 수 없기 때문에 **어셈블러(Assembler)**가 기계어로 번역해주어야 한다. 어셈블리어는 최근에도 속도가 중요한 곳에 쓰이고 있다. 그럼에도 어셈블리어로 프로그램 작성 시 간단한 작업을 수행하기 위해 많은 명령어가 필요했고 작성된 프로그램이 무슨 일을 하는 프로그램인지 이해하기 어려웠으며 이식성이 낮았다.

예) ```mov al, 061h```

## High-level Language
어셈블리어의 문제점을 해결하기 위해 C, C++, Pascal과 같은 **High-level 언어**가 등장하였다. 여기서 **High-level**이라는 말은 컴퓨터보다 인간에게 더 가깝다는 의미이다. **컴파일러**나 **인터프리터**를 거쳐 컴퓨터가 이해할 수 있도록 바꿔주어야 한다.

예) ```a = 97;```

### 컴파일러 (Compiler)
**컴파일러**는 소스 코드를 읽어서 이를 실행 가능한 프로그램으로 만들어준다. 때문에 프로그램을 실행할 때는 컴파일러가 필요하지 않다.  

![image](https://www.learncpp.com/images/CppTutorial/Chapter0/Compiling-min.png?ezimgfmt=rs:521x161/rscb2/ng:webp/ngcb2)

### 인터프리터 (Interpreter)
인터프리터는 소스 코드 내에 명령어들을 컴파일 과정 없이 바로 실행한다. 때문에 프로그램을 실행할 때마다 인터프리터를 거쳐야 한다.  

![image](https://www.learncpp.com/images/CppTutorial/Chapter0/Interpreting-min.png?ezimgfmt=rs:721x61/rscb2/ng:webp/ngcb2)

> 컴파일러와 인터프리터의 장단점 비교에 관한 글은 [여기](https://stackoverflow.com/questions/38491212/difference-between-compiled-and-interpreted-languages)를 참고.  

High-level 언어는 인간이 일상에서 사용하는 자연어와 가깝기 때문에 이해하고 작성하기가 쉬우며, 동일한 작업을 수행하는 프로그램 작성 시, 어셈블리어보다 프로그램이 간단하다. 또한 이식성이 좋아 CPU의 종류에 따라 다른 프로그램을 작성하지 않아도 된다.  

예)  
![image](https://www.learncpp.com/images/CppTutorial/Chapter0/Portability-min.png?ezimgfmt=rs:481x261/rscb2/ng:webp/ngcb2)

## 컴파일과 링크
코드를 작성하고 이를 실행 가능한 프로그램으로 만들 때 **컴파일**과 **링크**라는 과정을 거치게 된다. 이 두 과정을 합쳐서 **빌드**(Build)라고 한다.

### 컴파일 (Compile)
**컴파일러**(Compiler)가 각 소스 코드(.cpp 파일)에 대하여 C++ 언어의 규칙을 제대로 지키고 있는지 확인하고 이를 기계어로 된 **오브젝트 파일**(.o 또는 .obj 파일)로 변환하는 과정이다. 컴파일 과정에서 발생하는 에러를 컴파일 에러라 한다.

예)  
![image](https://www.learncpp.com/images/CppTutorial/Chapter0/CompileSource-min.png?ezimgfmt=rs:421x161/rscb2/ng:webp/ngcb2)

### 링크 (Link)
컴파일러가 오브젝트 파일을 만든 후, **링커**라는 프로그램이 앞에서 만들어진 오브젝트 파일들을 합쳐 하나의 실행 가능한 파일로 만든다. 여기서 추가적으로 다른 프로그램에서의 재사용을 위해 만들어진 **라이브러리 파일**도 링크할 수 있다. 라이브러리 파일에는 C++에서 제공하는 **표준 라이브러리**와 사용자가 추가한 외부 라이브러리들이 있다. 링커는 파일 간 종속성에 문제가 없는지 (예를 들어, 어떤 파일에서 사용하고 있는 무언가를 다른 파일에서 정의하지 않았다던가...) 확인한다. 만약 문제가 있다면 링커 에러가 발생한다.  

예)  
![image](https://www.learncpp.com/images/CppTutorial/Chapter0/LinkingObjects-min.png?ezimgfmt=rs:441x271/rscb2/ng:webp/ngcb2)

> 참고  
    1. [https://www.learncpp.com/cpp-tutorial/introduction-to-programming-languages/][Reference_1]  
    2. [https://www.learncpp.com/cpp-tutorial/introduction-to-the-compiler-linker-and-libraries/][Reference_2] 

[Reference_1]: https://www.learncpp.com/cpp-tutorial/introduction-to-programming-languages
[Reference_2]: https://www.learncpp.com/cpp-tutorial/introduction-to-the-compiler-linker-and-libraries/