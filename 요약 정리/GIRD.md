# 👑 SCSS Masterclass_ GRID
(S)CSS Layout Masterclass: Flexbox & Grid


# ==parents==
## ◼ display:grid
```css
 display:grid;
```
적용하고 싶은 `el`의 부모에게 `grid`를 준다.

## ◼ grid-template-columns/rows
```css
 grid-template-columns: ; -> 넓이
 grid-template-rows:;	-> 높이
```
### " line naming " 
##### parents
```css
grid-template-columns:
	[first-line] 100px
	[second-line] 100px
	[third-line] 100px
	[fourth-line] 100px  ;
	
grid-template-rows:  repeat(4,  100px  [sexy-line]);
```
- [] 안에 원하는 이름을 정해줘서 사용할수 있다.
##### child
```css
.content4{
	background-color:  #7bed9f;
	grid-column: first-line /fourth-line;
	grid-row: sexy-line 1 / sexy-line 3;
}
```

### "fr ( *fraction*)"

    grid-template-columns:  4fr  1fr  1fr  1fr;
![enter image description here](https://ifh.cc/g/o9eSLW.jpg)
- `grid` 안에서 가능하다
- 가능한 많은공간을 차지한다.(% 와 비슷한 기능)

## ◼ column/row-gap & gap
원하는 갯수 만큼 크기를 적어서 설정해 준다.
```css
 column-gap:;
 row-gap:;
 gap:; -> 한번에 간격을 정하고 싶을때에는 gap을 사용
```
el간의 간격을 나타내고 싶을때 사용.
## ◼ grid-template-areas
```css
grid-template-areas:
	"header header header header"
	"content content content nav"
	"content content content nav"
	"footer footer footer footer"
;
```
>영역별로 이름을 부여해줘서 넓이를 표현할수 있다.
>>`grid-template-areas:;`을 줬을 경우 자식 에게 해당 이름을 각각 부여해준다.
>>
>>       grid-area: header;

---

---
### 📐 함수 적용 하기
#### 1. repeat()
```css
 repeat(반복회수, 원하는 크기);
 
 grid-template-columns: auto 200px;
 -> 모든 공간을 사용한다.
```

#### 2. minmax()
```css
minmax(min, max)

grid-template-columns:  repeat(5,minmax(100px  ,  1fr));
```

#### 3. min-content / max-content
#### min-content
- content가 작아질 수 있는 만큼 작아지는것
#### max-content
- content가 커질수 있는 만큼 커지는것

ex)
```
grid-template-columns:  max-content  min-content;

```

> 좀더 유연한 반응형웹

```
grid-template-columns:repeat(5,minmax(max-content  ,1fr));
```

## ◼ justify-items/align-items

> 그리드 하나하나당  적용시키는 설정이다.

###  justify-items
```
justify-stretch:stretch ;
```
- dfault 
(자신의 몸에 맞게 자식들을 늘려서 맞춘다)
- 수평(가로)길이를 조정
```
justify-items:start;
```

### align-items
- 수직(세로)길이를 조정
```
align-items:start;
```


### 🔸 place-items
 ```
 place-items: align-items  justify-items;
 ```
- `align-items`와 `justify-items`를 한번에 사용할수 있다.

## ◼  justify-content / align-content

> 한줄 전체를 적용하는 설정이다

### justify-content

    justify-content:start

- default
- 가로축의 위치를 설정한다.
 ![enter
```
justify-content:center
```

### align-content

    align-content:start
- 세로축의 위치를 설정한다.


```
align-content:center
```

### 🔸 place-content
```
place-content:align-content justify-content
```
- `justify-content`와 `align-content`를 한번에 사용할수 있다.


## grid-auto-rows/ grid-auto-columns /grid-auto-flow
### grid-auto-rows/grid-auto-columns
```
grid-auto-rows:100px;
grid-auto-columns:100px
```

### grid-auto-flow
```
grid-auto-flow:  column;
```
- row의 수보다 더많은 div가 있을때 더많은 column을 만들어 낸다.



> 슬라이드 할때 유용함
```
grid-template-columns:  repeat(4,100px)  ;
grid-template-rows:  repeat(1,100px);

grid-auto-columns:  100px;
grid-auto-flow:  column;
```

- 일렬로 나열된다.
# ==child==

## ◼ grid-column-start/end
    grid-column-start:1 ;
    grid-column-end:5 ;
    
- grid-area 와 같은 효과 
- 라인으로 세어 준다.
- **시작과 끝이 항상 같이 존재 해야 한다!**
- 가로 길이를 설정 할수 있다.

## ◼ grid row-start/end

    gird-row-start:1;
    grid-row-end:3;
- 라인으로 세어준다
-  **시작과 끝이 항상 같이 존재 해야 한다!**
- 세로 길이를 설정 할수 있다.
## ◼grid-column/ grid-row

    grid-colum:시작/끝
    grid-row:시작/끝

- `grid-row-start/end` & `grid-column-start/end` 를 짧게 줄여 쓴것.

> 아이템의 숫자가 많을때 사용 맨 뒤의 라인을 쓰고 싶을때는 **-1** 을 사용하면 된다. 
> 
> `grid-column: span 4;` -> 설정한 갯수만큼의 상자로 채운다.
> `grid-row:  2/span 2;` ->2번째 줄부터 시작 해서 2개의 상자

## ◼ align-self/justify-self
### align-self / justify-self
```
align-self:  end;
align-self:  center;
-----------------------------------------------------------------
justify-self:  center;
justify-self:  end;
```


-각 cell들을 설정해준다.

### 🔸 place-self

    place-self: align-self justify-self;

- align-self 와 justify-self 를 한줄에 사용할수 있다.

## ◼ auto-fit / auto-fill


### auto-fill 
- 가능한 많이 알맞은 사이즈의 갯수로 채운다(갯수로 승부본다)

### auto-fit
- 1fr같이 넓이 자체를 늘려서 채운다.




