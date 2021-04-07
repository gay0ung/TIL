# 👑 FLEX



# parents
## flex-direction : row _ (default)

> ◾ Main Axis : horizontal(수평)
> ◾ Cross Axis : vertical (수직)
> 
 `justify-content: ;`
   수평축의 item 조정한다.

`align-itmes: ;` 
수직축의 item을 조정한다.

## flex-direction: column
> ◾ Main Axis : vertical (수직)
> ◾ Cross Axis : horizontal(수평)

 `justify-content: ;`
  수직축의  item 조정한다.
   
`align-itmes: ;` 
수평축의 item을 조정한다.

flex-box는 넓이를 정해 줘도 구겨서 같은 줄에 다 넣으려고 한다.
## flex-wrap
:nowrap; (_default)
:wrap -> 설정한 넓이를 유지한다.

## align-content: ;
  : 여러 줄사이의 간격을 조정해 준다.

## flex-flow: row wrap;
: flex-direction 과 flex-wrap을 한번에 사용할수 있다

# child
## align-self
: 자식에게 직접 적용한다.
## order
:순서를 부여해준다. (default:0)

## flex-shrink
 :1;   (_default)
정해진수의 배만큼 더 줄어 있다.

## flex-grow
:0;  (_default)
공간이 남아 있을때 공간을 차지 한다.

## flex-basis
: element의 기본값을 설정해 준다.(유동적으로 변하게 된다)
