---
layout: post
title: Study Note_Linear Algebrea Chaper 1  
tags:
  - Linear Algebra
  - Study
---

참고: 
Book: Strang, Linear Algebra and its applications
Reference: [https://twlab.tistory.com/](https://twlab.tistory.com/13?category=668741)

## Linear Algebra 선형대수학
### 1. 1 The Geometry of Linear Equations

선형 대수란 선형 방정식을 풀기 위한 방법론, 계수와 미지수는 행렬 (Matrix)로 표현이 가능 
- Coefficient Matrix
- Unknown Vector
- Right-hand Side Vector

Row: One Separate Equations (직선이나 평면의 방정식)  *Intersection of Planes*
- 각각의 방정식이 공간상에서 직선 또는 평면으로 표현되며, 방정식을 모두 만족시키는 해를 찾는 것 

Column: Linear Combination (벡터들의 선형 결합) *Combination of Columns*
- 예) 3차원 벡터들의 선형 결합 (Linear Combination); 좌변의 결합이 우변의 벡터를 만들어 냄


시스템의 해를 구하는 방법들은 아래와 같음 

1. Elimination 소거법 
2. Back-substitution - 후방 대입법 
3. Elimination Metrics 
4. Matrix multiplication

### 1.4 행렬 곱셈 (Matrix multiplication) 
C32 =  A (Row 3) X B (Column 2) —\> 벡터의 내적 *Dot Product*

M x N 행렬 A 와 N x P B행렬인 경우에만 곱이 가능하며, 곱의 결과 모양은 M (Rows of A) x P (Columns of B) 가 된다. 행렬을 곱할 때, 앞에 오는 행렬의 Column 값과 뒤 행렬의 Row 크기가 동일해야 곱이 가능하다. 


선형대수에서 Matrix Decomposition 이란, 어떤 행렬을 여러 행렬 곱으로 표현
*Decomposition의 목적은 1 ) 계산의 편리함, 2) 분석적 용이성을 위함이다.*

**앞으로 배우게 될 Decomposition(행렬 분해)의 종류와 특징을 잘 공부해서 과정을 이해해둘 것!**


### 1.5 LU Decomposition 
행렬 A가 있을 때, Lower Triangular Matrix와 Upper Triangular Matrix의 곱으로 분해

*단위 행렬을 만들기 위해 역행렬을 곱해줄 때는 각 행렬의 역행렬이 본래 자신과 붙을 수 있게, 행렬 곱셈의 반대 순서로 역행렬을 곱해줘야 함*

과정 

1. A 행렬을 소거하여 만들어지는 Upper Triangular Matrix 인 U행렬을 만들기 위해서 E21행렬을 만듬 (E21 -\> A 의 Row2, Column1의 원소를 제거 하기 위해서 Elementary Matrix)
2. 소거 행렬 Elimination Matrix E21의 역행렬이 L이다. 

#### LDU Decomposition
Pivot 값들을 따로 분해해야 하는 경우, U 행렬에 각 Pivot이 속해있는 Row를 해당 Pivot 으로 나눠줌. *D = Diagonal Matrix*

위의 경우는  2x2 Matrix 일 때의 과정이다. 만약 3x3Matrix 인 경우, 어떻게 될까? 
Row exchange 가 필요 없는 이상적인 경우에는, E32xE31xE21xA=U 로 되며, E21xE31xE32 의 역행렬의 곱이 L 이 됨. 

#### Permutations: 치환 행렬 
행 교환이 반드시 필요한 경우에는, 치환 행렬을 곱해주는 것 
행 교환이 필요한 A 행렬을 Decomposition 하는 경우에는 치환 행렬을 곱해서 PA = LU 모양으로 Decomposition  이 가능. 

*치환행렬은 Row를 바꿔주는 역을 함. 다시 원래대로 되돌려 놓기 위해서는 역행렬을 곱해주면 되는데 됨*

1. 모든 P 행렬은 Invertible 하다. 
2. P 행렬의 역행렬은 전치 행렬과 같다. 

### 1.6 Inverses and Transposes 

#### Transpose 전치 행렬
Row의 Items들이 Column 이 되며, Column 의 Items들이 Row가 되는 것 
대각선을 중심축으로 행렬을 180도 돌려서 뒤집는 것

#### Symmetric Matrix 대칭 행렬 
Transpose를 해서 행렬이 뒤집어져도 원래 행렬과 같은 특성을 지님
임의의 행렬 A와 그의 전치 행렬 At (Transpose)을 곱하면 항상 대칭 행렬 (Symmetric Matrix) 를 얻음 

#### 역행렬 (Inverse Matrix) 
- Invertible, Non-singular 
	- 행렬 A가 역행렬이 존재한다고 가정시, 행렬 A와 역행렬 A-1를 곱해주면 그 결과는 단위 행렬 (Identity matrix) 
	- 일반적으로 행렬의 곱셈은 순서에 따라 결과 값이 달라지나, 역행렬의 경우 순서가 바뀌어도 값이 변하지 않고 동일
	: No inverse, Singular 
	- 역행렬이 존재하지 않는 경우, 특이 행렬 (Singular matrix) 라고 함. 
	- 영행렬이 존재하지 않는 경우, 
		- det (A)  = 0
		- Column 행렬이 같은 라인에 위치 (Linearly Dependant) 
		- Linearly Independent인 차원의 개수 \< A의 전체 차원의 개수 
		- 각 Column을 정규화 해서 같은지 비교 
		- Ax=0을 만족하는 벡터 x 를 찾을 수 있다면, 그 행렬은 역행렬이 존재하지 않음., (단, A는 정방 행렬 & x 는 0이 아닌 벡터)
	- Gauss-Jordan Idea
		- 행렬 A에 역행렬을 곱하면, 그 결과는 단위 행렬 I가 되어야 한다. 
		- 우변에 Extra Column 벡터를 붙여서 Augmented Matrix 를 만들어서 소거법을 사용해서 풀었다면, Elimination Matrix를 만들어서 해결한다. 
		- A의 결과를 Upper Triangular Matrix로 완성 후, 반대로 아래에서 위쪽으로 Low Triangular을 만들기 위해서 소거를 진행
		- 단계별로 나오는 Elimination Matrix들의 곱 = E행렬은 A 행렬의 역행렬;

