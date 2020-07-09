---


---

<h1 id="📊-chart.js">📊 Chart.js</h1>
<p>◾ <a href="https://www.chartjs.org/"><strong>Chart.js 사이트</strong></a><br>
◾ <a href="https://github.com/chartjs/Chart.js"><strong>깃허브 다운로드 링크 :</strong></a><br>
◾ <a href="https://cdnjs.com/libraries/Chart.js"><strong>CDN :</strong></a><br>
◾ <a href="https://www.chartjs.org/samples/latest/"><strong>Chart sample</strong></a></p>
<h2 id="사용-예제">사용 예제</h2>
<pre class=" language-js"><code class="prism  language-js"><span class="token operator">&lt;</span>script<span class="token operator">&gt;</span> 
<span class="token keyword">var</span> ctx <span class="token operator">=</span> document<span class="token punctuation">.</span><span class="token function">getElementById</span><span class="token punctuation">(</span><span class="token string">'myChart'</span><span class="token punctuation">)</span><span class="token punctuation">;</span> 
<span class="token keyword">var</span> myChart <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">Chart</span><span class="token punctuation">(</span>ctx<span class="token punctuation">,</span> <span class="token punctuation">{</span> 
	type<span class="token punctuation">:</span> <span class="token string">'bar'</span><span class="token punctuation">,</span> 
	data<span class="token punctuation">:</span> <span class="token punctuation">{</span> 
		labels<span class="token punctuation">:</span> <span class="token punctuation">[</span>
			<span class="token string">'Red'</span><span class="token punctuation">,</span> <span class="token string">'Blue'</span><span class="token punctuation">,</span> <span class="token string">'Yellow'</span><span class="token punctuation">,</span> <span class="token string">'Green'</span><span class="token punctuation">,</span> <span class="token string">'Purple'</span><span class="token punctuation">,</span> <span class="token string">'Orange'</span>
		<span class="token punctuation">]</span><span class="token punctuation">,</span> 
		datasets<span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token punctuation">{</span> 
			label<span class="token punctuation">:</span> <span class="token string">'# of Votes'</span><span class="token punctuation">,</span>
			data<span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token number">12</span><span class="token punctuation">,</span> <span class="token number">19</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">3</span><span class="token punctuation">]</span><span class="token punctuation">,</span> 
			backgroundColor<span class="token punctuation">:</span> <span class="token punctuation">[</span> 
				<span class="token string">'rgba(255, 99, 132, 0.2)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(54, 162, 235, 0.2)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(255, 206, 86, 0.2)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(75, 192, 192, 0.2)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(153, 102, 255, 0.2)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(255, 159, 64, 0.2)'</span> 
			<span class="token punctuation">]</span><span class="token punctuation">,</span> 
			borderColor<span class="token punctuation">:</span> <span class="token punctuation">[</span> 
				<span class="token string">'rgba(255, 99, 132, 1)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(54, 162, 235, 1)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(255, 206, 86, 1)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(75, 192, 192, 1)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(153, 102, 255, 1)'</span><span class="token punctuation">,</span> 
				<span class="token string">'rgba(255, 159, 64, 1)'</span> 
			<span class="token punctuation">]</span><span class="token punctuation">,</span> 
			borderWidth<span class="token punctuation">:</span> <span class="token number">1</span> 
		<span class="token punctuation">}</span><span class="token punctuation">]</span> 
	<span class="token punctuation">}</span><span class="token punctuation">,</span> 
	options<span class="token punctuation">:</span> <span class="token punctuation">{</span> 
		responsive<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span> 
		scales<span class="token punctuation">:</span> <span class="token punctuation">{</span> 
			yAxes<span class="token punctuation">:</span> <span class="token punctuation">[</span><span class="token punctuation">{</span> 
				ticks<span class="token punctuation">:</span> <span class="token punctuation">{</span> b
					eginAtZero<span class="token punctuation">:</span> <span class="token boolean">true</span> 
				<span class="token punctuation">}</span> 
			<span class="token punctuation">}</span><span class="token punctuation">]</span> 
		<span class="token punctuation">}</span><span class="token punctuation">,</span> 
	<span class="token punctuation">}</span> 
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token operator">&lt;</span><span class="token operator">/</span>script<span class="token operator">&gt;</span>
</code></pre>
<h1 id="🔹-data"><em>🔹 data</em></h1>
<h3 id="◼-labels">◼ <strong>labels</strong></h3>
<p>: 데이터의 라벨을 입력하는 부분</p>
<h3 id="◼-data">◼ <strong>data</strong></h3>
<p>: 실제 값</p>
<h3 id="◼-backgroundcolor">◼ <strong>backgroundColor</strong></h3>
<p>: 데이터의 백그라운드 색상을 지정하는 부분</p>
<h3 id="◼-bordercolor">◼ <strong>borderColor</strong></h3>
<p>: 이름 그대로 border의 색상인데 선의 이나 태두리의 색이라고 보면 된다.</p>
<h3 id="◼--borderwidth">◼  <strong>borderWidth</strong></h3>
<p>: border의 굵기다.</p>
<h1 id="🔸-options"><em>🔸 options</em></h1>
<h3 id="◼-responsive">◼ responsive</h3>
<p><code>responsive</code>는 디폴트로 <code>true</code>로 되어 있어 <code>false</code>로 바꿔주지 않으면 canvas에 설정한 값과 달리 화면에 꽉차는 반응형으로 만들어 진다. canvas에 설정한 width값과 height값을 쓰려면  반드시 <code>false</code>로 바꾸어 주어야 한다.</p>
<h3 id="◼-scales">◼ scales</h3>
<p><strong>scales</strong>의  <strong>yAxes</strong> 는 y축에 관련된 옵션이고,  <strong>beginAtZero</strong>는 0부터 표기할지 이다.</p>
<h4 id="✂-label-제거-하기">✂ label 제거 하기</h4>
<pre class=" language-js"><code class="prism  language-js">options<span class="token punctuation">:</span>  <span class="token punctuation">{</span>
	legend<span class="token punctuation">:</span>  <span class="token punctuation">{</span>
		display<span class="token punctuation">:</span>  <span class="token boolean">false</span><span class="token punctuation">,</span>
	<span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">,</span>
</code></pre>
<hr>
<h4 id="참고">참고</h4>
<blockquote>
<h6 id="크기-조정하기"><a href="https://ming9mon.tistory.com/108?category=841705">크기 조정하기</a></h6>
<h6 id="데이터-세팅하기"><a href="https://ming9mon.tistory.com/109?category=841705">데이터 세팅하기</a></h6>
<h6 id="배경폰트라인-라벨-색상-변경"><a href="https://ming9mon.tistory.com/122?category=841705">배경,폰트,라인, 라벨 색상 변경</a></h6>
<h6 id="데이터-항상-보이게-설정"><a href="https://ming9mon.tistory.com/123?category=841705">데이터 항상 보이게 설정</a></h6>
<h6 id="y축-데이터-범위-설정"><a href="https://ming9mon.tistory.com/124?category=841705">y축 데이터 범위 설정</a></h6>
</blockquote>

