---
title:  "프로그래밍 언어에 관한 개론적인 이야기" 
excerpt: "프로그래밍 언어와 관련된 간단한 개념들을 정리하였습니다."

categories:
  -  talk
tags:
  - [Programming]

toc: true
toc_label: 목차
toc_sticky: true

date: 2023-01-17
last_modified_at: 2023-01-17
---

컴퓨터의 **프로그램**은 특정 작업을 실행하기 위해 수행할 수 있는 **명령어의 집합**이며 이러한 프로그램을 만드는 과정을 **프로그래밍**이라 한다.  

**프로그래머**는 명령어들이 적힌 하나 이상의 텍스트 파일, 즉 **코드**를 작성하여 프로그램을 만들고 이렇게 만들어진 프로그램은 컴퓨터의 메모리에 로드되어 실행된다.

## 기계어 (Machine Language)
컴퓨터의 CPU가 이해할 수 있는 명령어로 **Binary Digit (0과 1)**로 구성되어 있다.  

예) ```10110000 01100001```

## 어셈블리어 (Assembly Language)
**기계어**로 프로그램을 작성하는 것은 어렵고 시간이 많이 들어갔으며, 이식성이 낮아 CPU의 종류가 바뀌면 프로그램을 다시 작성해야 하는 번거로움이 있었다. 이를 해결하기 위해 만들어진 언어이며, CPU는 어셈블리어를 바로 이해할 수 없기 때문에 **어셈블러 (Assembler)**가 기계어로 번역해주어야 한다.  

예) ```mov al, 061h```

## High-level Language
**어셈블리어** 또한 인간이 이해하기 어려웠고 이식성이 낮았기 때문에 이를 해결하기 위해 C, C++과 같은 **High-level 언어**가 등장하였다. 여기서 **High-level**은 컴퓨터보다 인간에게 더 가깝다는 의미로, 이식성이 좋으며 프로그래머가 이해하기 쉽다. 당연히 컴퓨터는 이해할 수 없기 때문에 **컴파일러**나 **인터프리터**를 거쳐 컴퓨터가 이해할 수 있도록 바꿔주어야 한다.

예) ```a = 97;```

### 컴파일러 (Compiler)
**컴파일러**는 소스 코드를 읽어서 이를 실행 가능한 프로그램으로 만들어준다.

![image](https://www.learncpp.com/images/CppTutorial/Chapter0/Compiling-min.png?ezimgfmt=rs:521x161/rscb2/ng:webp/ngcb2)

컴파일러의 장점
* **컴파일러**는 모든 코드를 미리 볼 수 있기 때문에 **인터프리터**가 코드의 각 라인을 해석하는 것보다 코드의 최종 버전을 더 빠르게 실행하는 코드를 생성할 때 다양한 분석과 최적화를 수행할 수 있다.  

* 테이블 내부의 Memory lookup 측면에서 [Dynamic Dispatch][Dynamic_dispatch]나 상속과 같은 High-level 언어의 동일한 기능을 수행하는 Low-level 코드를 생성할 수 있다. 즉, 생성된 프로그램은 원래 코드의 정보를 덜 기억해도 되기 때문에 메모리 사용량을 줄일 수 있다.

* **인터프리터**의 경우, 실행되는 명령어는 일반적으로 프로그램에 **인터프리터**의 오버헤드 만큼 더해지지만, **컴파일러**는 오버헤드가 없으므로 더 빠르다.

컴파일러의 단점
* [Dynamic Typing][Dynamic_typing]과 같은 일부 언어 기능들은 실제로 프로그램이 실행되기 전까지 어떤 일이 일어날 지 모르기 때문에 효율적으로 컴파일하기 어려워 **컴파일러**가 아주 좋은 코드를 생성하지 못할 수도 있다.

* **컴파일러**는 분석을 수행하는 데 들어가는 시간이 길기 때문에 웹 브라우저와 같이 코드를 빠르게 로드하는 것이 중요한 설정에서 **컴파일러**는 자주 실행되지 않는 짧은 코드도 최적화하므로 속도가 느려질 수 있다.

### 인터프리터 (Interpreter)
인터프리터는 소스 코드 내에 명령어들을 컴파일 과정 없이 바로 실행한다.

![image](https://www.learncpp.com/images/CppTutorial/Chapter0/Interpreting-min.png?ezimgfmt=rs:721x61/rscb2/ng:webp/ngcb2)

인터프리터의 장점
* **인터프리터**는 작성된 대로 코드를 읽을 수 있고 코드를 생성하거나 최적화하기 위해 비용이 많이 들어가는 작업을 하지 않아도 되므로 **컴파일러**보다 실행이 빠르다.

* **인터프리터**는 프로그램 실행 중에 무엇을 하고 있는지 볼 수 있기 때문에 다양한 동적 최적화를 할 수 있다.

인터프리터의 단점
* **인터프리터**는 런타임에 프로그램이 이용 가능한 더 많은 정보를 유지해야 하므로 **컴파일러**보다 메모리 사용량이 더 많다.

* **인터프리터**는 **인터프리터**를 위해 코드 안에서 CPU 시간이 소비되기 때문에 실행 속도가 느려질 수 있다.

> 참고  
    1. [https://www.learncpp.com/cpp-tutorial/introduction-to-programming-languages/][Reference_1]  
    2. [https://stackoverflow.com/questions/38491212/difference-between-compiled-and-interpreted-languages][Reference_2]

[Dynamic_dispatch]: https://en.wikipedia.org/wiki/Dynamic_dispatch
[Dynamic_typing]: https://seongonion.tistory.com/16
[Reference_1]: https://www.learncpp.com/cpp-tutorial/introduction-to-programming-languages
[Reference_2]: https://stackoverflow.com/questions/38491212/difference-between-compiled-and-interpreted-languages