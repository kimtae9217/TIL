# [자료구조] 스택 (Python)

# 📕스택(Stack)

**스택(Stack)**이란? 

스택은 가장 나중에 들어온 데이터가 가장 먼저 처리되는 **후입선출** 구조 

즉, **`LIFO(Last-In-First-Out)`** 자료구조입니다. (* FILO = First-In-Last-Out 라고도 합니다 *)

스택의 동작은 다음과 같으며, 시간복잡도는 O(1)입니다.

- **push :** 스택 맨 끝(맨 위)에 데이터 삽입
- **pop :** 스택 맨 끝 데이터를 반환하는 동시에 제거
- **peek :** Top(맨 위)의 위치에 있는 데이터를 확인(반환만 하고 제거 x)
- **empty :** 스택이 비어있는지 확인
- **size :** 스택 크기를 확인

아래 그림과 같이 구멍이 하나밖에 없는 병이 있다고 생각하시면 이해하기 쉽습니다.

### 1. PUSH

![Untitled](https://user-images.githubusercontent.com/55828162/126887833-625cd478-d738-4046-863c-0d79238fb29d.png)

먼저 왼쪽 그림에서  빈 통을 스택 영역이라고 생각해봅시다.

### 스택에 새로운 데이터를 추가하는 것을 **PUSH** 라고 합니다.

왼쪽 그림과 같이 1이라는 데이터를 push합니다.

![Untitled 1](https://user-images.githubusercontent.com/55828162/126887834-c7e883bd-e2e4-4371-a372-4494bf515cb8.png)

데이터를 넣었으면 당연히 빼는 것도 있겠죠??

### 2. POP

1 위에 2와 3을 Push를 하게 되면 기존 데이터 위에 새 데이터가 순서대로 쌓여집니다.

![Untitled 2](https://user-images.githubusercontent.com/55828162/126887836-06340467-2dfa-4dde-be85-545f82b57267.png)

### **스택에 있던 데이터를 다시 빼내는 것을 POP 이라고 합니다.**

왼쪽 그림처럼 3을 POP 시키면 데이터가 빠져나오게 됩니다.

이처럼 스택은 기본적으로 PUSH와 POP을 통해 데이터의 추가/제거가 가능하며 PUSH/POP 되는 데이터의 크기는 사용자가 지정할 수있습니다.

스택이 밑에서부터 데이터를 추가하는 이유는 커널영역을 침범하지 않기 위해 밑에서부터 데이터를 추가합니다.

### **3. PEEK**

![Untitled 3](https://user-images.githubusercontent.com/55828162/126887838-3d8b0325-a897-469b-8416-5b4db8b0c2dd.png)

- peek은 Top(맨 위)의 위치에 있는 데이터를 확인하는 것을 말합니다.
- peek은 엿보다라는 뜻인데 즉, 최상단에있는 값을 반환만 하고 삭제는 하지 않습니다.

오른쪽 그림을 보면서 이해를 해봅시다.

현재  그림에서는 peek을 하게 되면 top위치에 있는 데이터 값은 2이기 때문에 2를 반환해줍니다. 

![Untitled 4](https://user-images.githubusercontent.com/55828162/126887841-ebdd84d3-2ae7-4c19-90b5-a8d86a752638.png)

만약에 3을 push하게 되면 peek을 하게되면 top의 위치에 있는 데이터 값이 3이기 때문에 3을 반환해줍니다.

### 스택(Stack) 구현

파이썬에서는 스택을 리스트로 구현을 할 수 있는데 간단하게 보여드리겠습니다.

파이썬에서는 다음과 같이 리스트의 append() 와 pop() 메서드로 스택을 구현이 가능합니다.

먼저 빈 스택(리스트)를 초기화합니다.

- **Stack - init**

```python
stack = []
```

- **Stack - push**

스택에 원소를 넣을 때는 append() 메서드를 이용해 리스트의 가장 마지막에 원소를 넣도록 합니다.

```python
stack = [1, 2, 3]
stack.append(4)

print(stack)

# 결과 : [1, 2, 3, 4] 
```

- **Stack - pop**

스택에서 원소를 제거할 때는 pop() 메서드를 이용해 리스트의 가장 마지막 원소를 제거해줍니다.

이때, pop 메서드에 의해 제거한 원소를 리턴 받을 수 있습니다.

```python
stack = [1, 2, 3]
stack.append(4)
stack.pop()

print(stack)

# 결과 : [1, 2, 3]
```

- **Stack - peek**

스택에서 원소를 제거하지 않고 top에 무엇이 있는지 확인하고 가져오고 싶을 때 [-1]을 이용합니다. 

```python
stack = [1, 2, 3]
stack.append(4)
stack.pop()

peek = stack[-1] # 맨 위 데이터 값 확인
 
print(peek)

# 결과 : 3
```



### 🖥️ 관련 문제

### 백준[10828] 스택 문제

[10828번: 스택](https://www.acmicpc.net/problem/10828)