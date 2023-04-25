# Frame

<br>

**superview의 좌표계에서 해당 view의 위치와 크기를 나타낸다**
<br><br>

## frame의 origin(x, y)

<br>

frame이 나타내는 origin(x, y) 좌표는 Super View의 원점을 (0, 0)으로 놓고

원점으로부터 얼마나 떨어져 있는지를 나타낸 것 (원점이란 View의 가장 왼쪽, 가장 윗 부분을 말함)

<br><br>

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FPPd9G%2FbtqL2PkesNl%2F46dwzhgECMK18mM8G2CCKK%2Fimg.png)

firstView의 SuperView는 **루트View**

**루트 View의 원점을 기준**으로 **x축으로 20,y축으로 50** 이므로 (20, 50)

<br><br>

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbrWnxX%2FbtqLZKxdAgw%2FS08euXvkx7nPHCUAag5Kdk%2Fimg.png)

secondView의 Super View는 **firstView**

firstView의 원점의 좌표는 (20, 50)이지만 **원점에서 얼만큼 떨어져 있는지가** 중요

**firstView의 원점을 기준**으로 **x축으로 10, y축으로 10 이므로** (10, 10)

<br><br><br>

## frame의 size(width, height)

<br>

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FblGhmq%2FbtqLTyLWYgT%2FkTzbqxNij5BkGmnHNNF0x1%2Fimg.png)

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcG2Tof%2FbtqLRU2vVaV%2Funr8fQGs3Ts7vW6TYqRf81%2Fimg.png)


width = 200, height = 130인 ****View ****를 회전시키면

width와 hright는 건들지 않았는데도 사이즈가 변한다

<br>

frame의 size는 **View 자체의 크기가 아닌 View가 차지하는 영역을 모두 감싸는 사각형**으로 나타낸 것이기 때문

그에 따라 frame의 **origin 값도 변경될 수 있다**

회전시켰을 땐 진짜 View의 size (200, 130)를 알기 위해서는 **bounds** 사용
