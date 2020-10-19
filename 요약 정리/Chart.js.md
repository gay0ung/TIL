# 📊 Chart.js
◾ [**Chart.js 사이트**](https://www.chartjs.org/)
◾ [**깃허브 다운로드 링크 :**](https://github.com/chartjs/Chart.js) 
◾ [**CDN :**](https://cdnjs.com/libraries/Chart.js)
◾ [**Chart sample**](https://www.chartjs.org/samples/latest/) 
◾ [chart.js-plugin-datalabels](https://chartjs-plugin-datalabels.netlify.app/)

## 사용 예제
```js
<script> 
var ctx = document.getElementById('myChart'); 
var myChart = new Chart(ctx, { 
	type: 'bar', 
	data: { 
		labels: [
			'Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'
		], 
		datasets: [{ 
			label: '# of Votes',
			data: [12, 19, 3, 5, 2, 3], 
			backgroundColor: [ 
				'rgba(255, 99, 132, 0.2)', 
				'rgba(54, 162, 235, 0.2)', 
				'rgba(255, 206, 86, 0.2)', 
				'rgba(75, 192, 192, 0.2)', 
				'rgba(153, 102, 255, 0.2)', 
				'rgba(255, 159, 64, 0.2)' 
			], 
			borderColor: [ 
				'rgba(255, 99, 132, 1)', 
				'rgba(54, 162, 235, 1)', 
				'rgba(255, 206, 86, 1)', 
				'rgba(75, 192, 192, 1)', 
				'rgba(153, 102, 255, 1)', 
				'rgba(255, 159, 64, 1)' 
			], 
			borderWidth: 1 
		}] 
	}, 
	options: { 
		responsive: false, 
		scales: { 
			yAxes: [{ 
				ticks: { b
					eginAtZero: true 
				} 
			}] 
		}, 
	} 
});
</script>
```
# _🔹 data_ 
### ◼ **labels** 
 : 데이터의 라벨을 입력하는 부분

### ◼ **data** 
: 실제 값

### ◼ **backgroundColor**  
: 데이터의 백그라운드 색상을 지정하는 부분

### ◼ **borderColor**  
: 이름 그대로 border의 색상인데 선의 이나 태두리의 색이라고 보면 된다.

### ◼  **borderWidth**
: border의 굵기다.

# _🔸 options_ 
### ◼ responsive

`responsive`는 디폴트로 `true`로 되어 있어 `false`로 바꿔주지 않으면 canvas에 설정한 값과 달리 화면에 꽉차는 반응형으로 만들어 진다. canvas에 설정한 width값과 height값을 쓰려면  반드시 `false`로 바꾸어 주어야 한다.

### ◼ scales
**scales**의  **yAxes** 는 y축에 관련된 옵션이고,  **beginAtZero**는 0부터 표기할지 이다.


#### ✂ label 제거 하기
```js
options:  {
	legend:  {
		display:  false,
	},
},
```

# _🔸 plugin_
##### plugin npm 설치
```
npm install chartjs-plugin-datalabels --save
```
#### 데이터값 항상 보이게 하기.
```js
plugins:  {
	datalabels:  {
		color: '#6669',
		anchor: 'end',
		align: 'left',	
		offset: context => {
			 let index = context.dataIndex;
			 let model =		 context.dataset._meta[Object.keys(context.dataset._meta)[0]].data[index]._model;
			 let textX = model.x > 100 ? '0' : '-45';
			 return textX;
		},
	},
},
```

----
#### 참고

> ###### [크기 조정하기](https://ming9mon.tistory.com/108?category=841705)
> ######  [데이터 세팅하기](https://ming9mon.tistory.com/109?category=841705)
> ######  [배경,폰트,라인, 라벨 색상 변경](https://ming9mon.tistory.com/122?category=841705)
> ###### [y축 데이터 범위 설정](https://ming9mon.tistory.com/124?category=841705)



