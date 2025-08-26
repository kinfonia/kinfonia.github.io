---
date: '2025-08-26T13:20:52+09:00'
title: '대칭적분방정식 copy'
math: true
draft: false
tags:
  - Analysis-Calculus
  - LinearAlgebra
---
**Reflection Integral Equation**, $\text{RIE by Kunwoo Park}$ at July 1st, 2024
# 공식
좌표평면 $S_2=\mathbb{R}^2$ 위의 **함수** $f$와 정점 $p(x_p,y_p)$에 대한 $f$의 $p$에 대한 [[대칭이동 횟수의 확장정의|확장된 대칭이동]]된 함수 $\mathbf{T}_{\alpha,\beta}(f)_p$ 의 고정된 적분영역 $[a,b]$ 위의 넓이는 아래와 같다.

$$\int_{a}^{b} \mathbf{T}_{\alpha, \beta}\{\{f\}} _p(x)$$

$$\int_{a}^{b} \mathbf{T}_{\alpha,\beta}\{f\} _p \,(x)\, \mathrm{d} x= y_p (b-a)(1-e^{\beta \pi i}) + e^{(\beta - \alpha ) \pi i}\int_{a'}^{b'}f(x) \, \mathrm{d}x$$
<!-- 
- *축약표기:* $A'=x_p(1-e^{\alpha \pi i})+e^{\alpha \pi i}A$
## 증명
본문인데
아니 왜 본문이 이렇게 ㅋ큰거야
음
[[대칭이동 횟수의 확장정의]]로부터 아래와 같이 쓸 수 있다.
$$
\mathbf{T}_{\alpha,\beta}(f)_p =
\begin{pmatrix}x_p (1-e^{\alpha \pi i} )+e^{\alpha \pi i}x\\y_p (1-e^{\beta \pi i} )+e^{\beta \pi i}y\end{pmatrix}$$
이때 $f$가 **함수**라면, $y=f(x)$ 이므로 아래와 같이 쓸 수 있다.
$$
\mathbf{T}_{\alpha,\beta}(f)_p =
y_p(1-e^{\beta \pi i}) + e^{\beta \pi i} f(x_p(1-e^{\alpha \pi i })+e^{\alpha \pi i}x)
$$
이는 아래의 $\mathbf{T}_{1,1}(f)_p$ 로부터 바로 생각할 수 있다.
$$
f(x) \rightarrow \underbrace{2y_p -f}_{\text{outside}}(\underbrace{2x_p -x}_{\text{inside}})
$$
아무튼 이 $\mathbf{T}_{\alpha,\beta}(f)_p$ 를 고정된 구간 $[a,b]$ 위에서 치환적분을 이용해 적분하면 식을 얻는다.
$$
\begin{align}
\text{we want: }I=\int_{a}^{b} \mathbf{T}_{\alpha,\beta}(f) _p \, \mathrm{d} x 
=
\int_{a}^{b}y_p(1-e^{\beta \pi i}) + e^{\beta \pi i} f(\underbrace{x_p(1-e^{\alpha \pi i })+e^{\alpha \pi i}x}_{x'}) \, \mathrm{d}x
\\
= \int_{a'}^{b'}\left\{ y_p (1-e^{\beta \pi i}) +e^{\beta \pi i} f(u) \right\}\cfrac{{\mathrm{d}}u }{e^{\alpha \pi i}} \, \text { as }x' \rightarrow u
\\
= \underbrace{\cfrac{1}{e^{\alpha \pi i}}\int_{a'}^{b'} y_p(1-e^{\beta\pi i}) \, \mathrm{d}u}_C + \cfrac{e^{\beta \pi i}}{e^{\alpha \pi i}} \int_{a'}^{b'} f(u)\, \mathrm{d}u
\\
C = \cfrac{y_p (1-e^{\beta \pi i})}{e^{\alpha \pi i}} \cdot 1 \bigg\rvert _{a'}^{b'} = \cfrac{y_p (1-e^{\beta \pi i})}{\cancel{e^{\alpha \pi i}}} \cdot (b-a) \cdot \cancel{ e^{\alpha \pi i}}
\\
\therefore I = y_p(b-a)(1-e^{\beta \pi i}) + e^{(\beta- \alpha) \pi i} \int_{a'}^{b'} f(x) \, \mathrm{d}x \, \blacksquare
\end{align}
$$
## 특수경우
- $\alpha=\beta$ 일 경우, 아래와 같이 깔끔한 식을 얻는다.$$
  \int_{a}^{b}\tau_\alpha(f)_p \, \mathrm{d} x = y_p(b-a)(1-e^{\alpha \pi i})+ \int_{a'}^{b'} f(x) \, \mathrm{d}x  $$
- 더 나아가 [[타우 변환, 타우-오 변환]]의 경우, 아래와 같이 깔끔한 식을 얻는다.$$\int_{a}^{b}\tau_\alpha(f)_{\mathbf{o}}  \, \mathrm{d} x = \int_{ae^{\alpha \pi i}}^{be^{\alpha \pi i}} f(x) \, \mathrm{d}x$$
# 의미 분석

# 예시
## 정사각형 대칭시키기
정사각형 $R=[0,r] \times [0,r]$ 에 대해 생각해보자. 원래 넓이는 $r^2$인데, 한번 대칭이동해보자. 원점에 대하여 $\alpha$번 대칭이동하였을때 $R$의 넓이를 $S_{\alpha}$라고 하면, 대칭적분방정식에 따라 아래와 같다.
$$
S_\alpha =\int_{0}^{r}\tau_\alpha(R)_{\mathbf{o}}  \, \mathrm{d} x = \int_{0}^{re^{\alpha \pi i}} r \, \mathrm{d}x
\\
= r^2
e^{\alpha \pi i}$$
특히 $\alpha=1/2$ 인 경우, 넓이는 원래 넓이의 단위허수배 $ir^2$가 된다.

## 이등변삼각형 대칭시키기
구간 $[0,r]$ 위에서  함수 $f(x)=x$ 에 대칭이동을 적용한 함수 $\mathbf{T}_{\alpha,\alpha}(x)_\mathbf{o} \, \mathrm{d}x$ 에 대해 다루어보자.

$$
\begin{align*}
\int_{0}^{r} \mathbf{T} _{\alpha , \alpha} (x) _{\mathbf{o}} \, \mathrm{d} x =  \int_{0}^{re^{\alpha \pi i}} x \, \mathrm{d} x
\\
= \cfrac{r^2e^{2\alpha \pi i}}{2}
\end{align*}
$$
# 활용
만약 대칭횟수 $\alpha,\beta$ 를 $x$에 대한 함수로, 즉 매개변수화한다면 어떻게 될까?
아래 raw한 대칭적분방정식을 불러오자.
$$
I : \int_{a}^{b}\mathbf{T}_{\alpha,\beta}(f)_p  \, \mathrm{d}x = \int_{a}^{b} y_p (1-e^{\beta \pi i}) + e^{\beta \pi i}f(x_p(1-e^{\alpha \pi i})+e^{\alpha \pi i}x)
$$
이때 $\alpha(x),\beta(x)$ 로 매개변수화한다면 좀 복잡해진다.(굳이 쓰지는 않음)
그러나 $\alpha(x)=0, p=\mathbf{o}(0,0)$ 인 특수한 경우를 보자면 아래와 같이 쓸 수 있다.
$$
I: \int_{a}^{b} \mathbf{T}_{0,\beta(x)}(f)_\mathbf{o} \, \mathrm{d} x = \int_{a}^{b} e^{\beta (x)\pi i} f(x) \, \mathrm{d}x
$$
이때 적분구간 $[a,b]$를 naive하게 무한대 구간 등으로 잘 잡으면 여러 변환이나 함수들과의 관계를 얻을 수 있다. (그러니까 기하적으로 의미를 살짝 엿볼 수 있다)
### 변환
#### 푸리에 변환
$$
\begin{align*}
\hat {f}(t) \equiv \int_{-\infty}^{\infty} e^{-2\pi i t x} f(x) \, \mathrm{d}x
\\
= \int_{-\infty}^{\infty} \mathbf{T}_{0,-2tx}(f)_\mathbf{o} \, \mathrm{d}x 
\end{align*}
$$
#### 라플라스 변환
$$
\begin{align*}
\mathcal{L}\{f\}(s) \equiv \int _{0}^{\infty} e^{-st} f(t) \, \mathrm{d}t
\\
= \int_{0}^{\infty} \mathbf{T} _0,{-\tfrac{st}{\pi i}} (f)_\mathbf{o} \, \mathrm{d}t
\end{align*}
$$
### 함수
#### 감마 함수
$$
\begin{align*}
\Gamma(z) = \int_{0}^{\infty} t^{z-1} e^{-t} \,\mathrm{d}t
\\
= \int_{0}^{\infty}\mathbf{T}_0 , \tfrac{ti}{\pi} (t^{z-1})_{\mathbf{o}} \, \mathrm{d}t
\end{align*}
$$
예를 들어 $\Gamma(1)$에 대한 대칭의 의미로 해석해보자.
$$
\Gamma(1) = \int_{0}^{\infty} \mathbf{T}_{0, \tfrac{ti}{\pi}}(1)_{\mathbf{o}} \, dt = 0! =1
$$
즉 상수함수 $f(t)=1$ 을 $t=0 \text{ to } \infty$ 에서 $y$축에 대해 각 $t$에서 $\cfrac{ti}{\pi}$ 번 대칭한 함수의 함숫값을 각 지점에서 적분값을 긁어모으면 $1$이 된다는 것이다.
#### 지수 적분 함수
$$
\begin{align*}
\mathrm{Ei}(x) = -\int_{-x}^{\infty} \cfrac{e^{-t}}{t}  \, \mathrm{dt}
\\
=- \int_{-x}^{\infty} \mathbf{T}_{0,\tfrac{ti}{\pi}}\left(\cfrac{1}{t}\right)_{\mathbf{o}} \, \mathrm{d} t 
\end{align*}
$$ -->
