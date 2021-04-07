# 👑 SCSS

##  Variables

- 폴더명 맨 앞에 `_` 를 넣어준다

### ex.
##### style.scss
```scss
@import  '_variables';
h2  {
	color: $bg;
}
```
- `@import` 해준뒤 사용해준다.
##### _variables.scss
```scss
$bg:#e7473c;
$title:32px;
```



## Nesting
- 같은 부모 선상에 있는 el들을 한곳에 써줄수 있다
- 가독성이 좋다.
``` scss
.box  {
	margin-top:20px;
	h2  {
		color:  blue;
		&:hover{
			color:  white;
		}
	}
	button{
		color:  red;
	}
	&:hover{
		background-color:  green;
	}
}
```

## Mixins
- 폴더명 맨 앞에 `_` 를 넣어준다


### ex.
##### style.scss
```scss
@import  '_mixins';
a  {
	margin-bottom:  10px;
	&:nth-child(odd){
		 @include link(rgb(43, 160, 39))
	}
	&:nth-child(even){
		 @include link(rgb(70, 104, 55))
	}
}
```
- `@import` 해준뒤 사용해준다.
- `@include`  로 사용할수 있다.
##### _ mixins.scss
```scss
 @mixin link($color) {
	 text-decoration: none;
	 display: block;
	 color: $color;
	 font-weight: bold;
 }
```  


### 객체를 함수형식으로 이용할수 있다.
##### style.scss
```scss
@import  '_mixins';
a  {
	margin-bottom:  10px;
	&:nth-child(odd){
		@include  link("odd")
	}
	&:nth-child(even){
		@include  link("even")
	}
}
```
- `@import` 해준뒤 사용해준다.
- `@include`  로 사용할수 있다.
##### _ mixins.scss
```scss
@mixin  link($word)  {
	text-decoration:  none;
	font-weight:  bold;
	display:  block;
	@if $word ==  'odd'  {
		color:  blueviolet;
	}  @else{
		color:  coral;
	}
}
```
##   Extend
- 비슷한 코드가 중복될경우  유용하다.
- 폴더명: `_중복할el`

##### style.scss
```scss
@import  '_buttons';
a {
	color:  white;
	display:  inline;
	@extend  %button;
}
button {
	@extend  %button;
}
```
- `@import` 해준뒤 사용해준다.
- `@extend`로 받아와 사용한다.
##### _buttons.scss
```scss
%button  {
	border-radius:  7px;
	font-size:  15px;
	text-transform:  uppercase
	padding:  5px  10px;
	background-color:  peru;
	font-weight:  bold;
}
```
- `%` 를 이용해 생성한다.
##   Responsive Mixins
- 반응형 웹을 만들수 있다.
##### style.scss
```scss
p  {
	font-weight:  bold;
	font-size:  2em;
	color:  red;
	@include  responsive("iphone"){
		color:  rgb(190,  156,  6);
	}
	@include  responsive("iphone-l"){
		color:  rgb(190,  156,  6);
	}
	@include  responsive("tablet"){
		color:  rgb(102,  0,  128)
	}
}
```

##### _mixins.scss
```scss
$minIphone:  500px;
$maxIphone:  690px;

$minTablet: $minIphone +  1;
$maxTablet:  1120px;
  
@mixin  responsive($device)  {
	@if $device ==  'iphone'{
		@media  screen  and  (min-width:$minIphone)  
		and  (max-width:$maxIphone)  {
		@content;
		}
	}@else if $device ==  'tablet'  {
		@media  screen  and  (min-width:$minTablet) 
		and  (max-width:$maxTablet)  {
		@content;
		}
	}@else if $device ==  'iphone-l'  {
		@media  screen  and  (min-width:$minIphone)  
		and  (max-width:$maxIphone)  and  (orentation:landscape){
		@content;
		}
	}@else if $device ==  'ipad-l'  {
		@media  screen  and  (min-width:$minIphone)  
		and  (max-width:$maxIphone)and  (orentation:landscape){
		@content;
		}
	}
}
```

✔ 참고

> [Bourbon](https://www.bourbon.io/)
> [bourbon Documentation](https://www.bourbon.io/docs/latest/)


