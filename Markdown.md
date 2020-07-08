---


---

<h1 id="markdown">Markdown</h1>
<p>일반 텍스트 문서의 양식을 편집하는 문법. README파일이나 오라인 문서, 혹인 일반 텍스트 편집기로 문서 양식을 편집할 때 쓰인다. 마크다운을 이용해 작성도니 문서는 쉽게 HTML 등 다른 문서형태로 변환 가능 하다.</p>
<h1 id="📖-how-to-use">📖 how to use?</h1>
<h1 id="제목header">1. 제목(header)</h1>
<p>✍ <strong>작성</strong></p>
<pre><code># h1
## h2
### h3
#### h4
##### h5
###### h6
</code></pre>
<h1 id="문단-간격">2. 문단 간격</h1>
<p>문단의 간격은 줄 바꿈 으로 나타내며, 여러번 줄 바꿈 시 <code>&lt;br/&gt;</code>을 사용하면 가능.</p>
<p>✍ <strong>작성</strong></p>
<pre><code>첫 번째 &lt;br/&gt;&lt;br/&gt;
두 번째
</code></pre>
<p>👉 <strong>결과</strong></p>
<p>첫 번째 <br><br><br>
두 번째</p>
<h1 id="목록list">3. 목록(list)</h1>
<p>순서를 표기하는 목록/ 순서가 없는 목록 두가지 작성 가능</p>
<h3 id="순서를-표기하는-목록">3.1 순서를 표기하는 목록</h3>
<p><code>숫자</code>와  <code>.</code>을 사용하여 작성합니다.</p>
<p>✍ <strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">1. 첫 번째
2. 두 번째
3. 세 번째
</code></pre>
<p>👉 <strong>결과</strong></p>
<ol>
<li>첫 번째</li>
<li>두 번째</li>
<li>세 번째</li>
</ol>
<h3 id="순서가-없는-목록">3.2 순서가 없는 목록</h3>
<p><code>-</code>,  <code>*</code>,  <code>+</code>  을 사용 하여 작성합니다. (셋 다 동일하게 작성됩니다.)<br>
인라인 코드, 블럭 코드를 작성할 수 있으며  <code>Tab</code>키나  <code>스페이스 바</code>를 이용해 들여쓰기가 가능합니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">- 순서 없는 목록 1
    - 목록 1.1
        - 목록 1.2
- 순서 없는 목록 2
		
        Tab 두번 하면 코드 블럭을 만들 수 있어요.
* 순서 없는 목록 3
+ 순서 없는 목록 4
	+ `인라인 코드 가능`
    	+ 들여쓰기(tab키 이용)를 하면 다른 모양으로 표현 됩니다.
        
        ```　
		블럭 코드 가능
		```　
</code></pre>
<p>👉 <strong>결과</strong></p>
<ul>
<li>
<p>순서 없는 목록 1</p>
<ul>
<li>목록 1.1
<ul>
<li>목록 1.2</li>
</ul>
</li>
</ul>
</li>
<li>
<p>순서 없는 목록 2</p>
<pre class=" language-null"><code class="prism  language-null">  Tab 두번 하면 코드 블럭을 만들 수 있어요.
</code></pre>
</li>
<li>
<p>순서 없는 목록 3</p>
</li>
<li>
<p>순서 없는 목록 4</p>
<ul>
<li><code>인라인 코드 가능</code></li>
<li>들여쓰기(tab키 이용)를 하면 다른 모양으로 표현 됩니다.</li>
</ul>
<pre class=" language-null"><code class="prism  language-null"></code></pre>
<pre><code>	블럭 코드 가능
	```
</code></pre>
<pre><code></code></pre>
</li>
</ul>
<h2 id="폰트-스타일">4. 폰트 스타일</h2>
<p>굵게, 기울이기, 취소선 등 기본적인 스타일을 아래와 같이 작성할 수 있습니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">__굵게__
**굵게**
_기울여 쓰기_
*기울여 쓰기*
~취소선~
~~취소선~~
</code></pre>
<p>👉 <strong>결과</strong></p>
<p><strong>굵게</strong><br>
<strong>굵게</strong><br>
<em>기울여 쓰기</em><br>
<em>기울여 쓰기</em><br>
<sub>취소선</sub><br>
취소선</p>
<h2 id="인용문">5. 인용문</h2>
<p>인용문을 작성할 때에는  <code>&gt;</code>를 사용합니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">&gt; 인용문 작성하기
-작성자

&gt; 인용문 작성하기
&gt;&gt; (&gt;)의 갯수에 따라
&gt;&gt;&gt; 중첩문 가능
</code></pre>
<p>👉 <strong>결과</strong></p>
<blockquote>
<p>인용문 작성하기<br>
-작성자</p>
</blockquote>
<blockquote>
<p>인용문 작성하기</p>
<blockquote>
<p><code>&gt;</code>의 갯수에 따라</p>
<blockquote>
<p>중첩문 가능</p>
</blockquote>
</blockquote>
</blockquote>
<h2 id="인라인-코드">6. 인라인 코드</h2>
<p><code>백틱(｀)</code>을 사용하여 인라인 코드를 작성할 수 있습니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">`인라인 코드는 이렇게 작성해요.`
</code></pre>
<p>👉 <strong>결과</strong></p>
<p><code>인라인 코드는 이렇게 작성해요.</code></p>
<h2 id="여러-줄로-된-코드-블럭">7. 여러 줄로 된 코드 블럭</h2>
<p><code>백틱(｀)</code>을 세 개 사용하여 작성할 수 있습니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">```　
위 아래 3개로 감싸면 블럭으로 만들 수 있어요.
```　
</code></pre>
<p>👉 <strong>결과</strong></p>
<pre class=" language-null"><code class="prism  language-null">위 아래 3개로 감싸면 블럭으로 만들 수 있어요.
</code></pre>
<h3 id="🧐-코드-하이라이트">🧐 코드 하이라이트</h3>
<p>✍<strong>작성</strong></p>
<pre><code>```javascript
let sumNumbers = (firstNum, lastNum) =&gt; {
  return firstNum + lastNum;
};
sumNumbers(100, 200);
```
</code></pre>
<p>👉 <strong>결과</strong></p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">let</span> <span class="token function-variable function">sumNumbers</span> <span class="token operator">=</span> <span class="token punctuation">(</span>firstNum<span class="token punctuation">,</span> lastNum<span class="token punctuation">)</span> <span class="token operator">=&gt;</span> <span class="token punctuation">{</span>
  <span class="token keyword">return</span> firstNum <span class="token operator">+</span> lastNum<span class="token punctuation">;</span>
<span class="token punctuation">}</span><span class="token punctuation">;</span>
<span class="token function">sumNumbers</span><span class="token punctuation">(</span><span class="token number">100</span><span class="token punctuation">,</span> <span class="token number">200</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="링크link">8. 링크(link)</h2>
<p>인라인 링크와 url 링크, 참조 링크로 나타낼 수 있습니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">인라인 링크는 아래처럼
[인라인 링크](https://velog.io/)

url 링크는 아래처럼
&lt;https://velog.io/&gt;

참조 링크
[velog]:(https://velog.io/)
</code></pre>
<p>👉 <strong>결과</strong></p>
<p>인라인 링크는 아래처럼<br>
<a href="https://velog.io/">인라인 링크</a></p>
<p>url 링크는 아래처럼<br>
<a href="https://velog.io/">https://velog.io/</a></p>
<p>참조 링크<br>
[velog]:(<a href="https://velog.io/">https://velog.io/</a>)</p>
<h2 id="수평선">9. 수평선</h2>
<p><code>*</code>이나  <code>-</code>,  <code>_</code>  등을 3개 이상 입력하면 작성할 수 있습니다.<br>
띄어쓰기를 중간에 삽입하여도 가능합니다. 다만, 하이픈<code>-</code>은 헤더로 인식할 수도 있으니 주의해서 사용할 필요가 있습니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">***
-----
__ __ __ __ __ __ __
</code></pre>
<p>👉 <strong>결과</strong></p>
<hr>
<hr>
<hr>
<h2 id="테이블table">10. 테이블(Table)</h2>
<p>테이블은 아래와 같이 작성합니다.<br>
<code>|</code>  로 구분하며,  <strong>&lt;4. 폰트 스타일&gt;</strong>  에서 이야기 했던 기본적인 스타일 적용이 가능합니다. 또한  <code>-(하이픈)</code>으로 구분된 곳 각각 왼쪽, 양쪽, 오른쪽에  <code>:(세미콜론)</code>을 붙일 경우 순서대로 왼쪽 정렬, 가운데 정렬, 오른쪽 정렬이 가능합니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">| 드라마 제목 | 주연 배우 | 방영일 |
|:----------|:----------:|----------:|
| **호텔 델루나** | 이지은, 여진구 | ~~2019.07.13. ~ 2019.09.01.~~ |
| 타인은 지옥이다 | 임시완, 이동욱, 이현욱, 이정은 | 2019.08.31. ~ |
| 멜로가 체질 | 천우희, 안재홍, 전여빈, 공명 | 2019.08.09. ~ |
</code></pre>
<p>👉 <strong>결과</strong></p>

<table>
<thead>
<tr>
<th align="left">드라마 제목</th>
<th align="center">주연 배우</th>
<th align="right">방영일</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><strong>호텔 델루나</strong></td>
<td align="center">이지은, 여진구</td>
<td align="right"><s>2019.07.13. ~ 2019.09.01.</s></td>
</tr>
<tr>
<td align="left">타인은 지옥이다</td>
<td align="center">임시완, 이동욱, 이현욱, 이정은</td>
<td align="right">2019.08.31. ~</td>
</tr>
<tr>
<td align="left">멜로가 체질</td>
<td align="center">천우희, 안재홍, 전여빈, 공명</td>
<td align="right">2019.08.09. ~</td>
</tr>
</tbody>
</table><h2 id="체크박스check-box">11. 체크박스(Check Box)</h2>
<p><code>-</code>,  <code>*</code>,  <code>+</code>  뒤에 띄어쓰기 후  <code>대괄호</code>를 넣어 작성해주세요.  <code>대괄호</code>안에 띄어쓰기를 하면 빈 체크박스,  <code>x</code>를 넣으면 체크된 체크박스가 생깁니다.</p>
<p>✍<strong>작성</strong></p>
<pre class=" language-null"><code class="prism  language-null">- [ ] 운동 하기
- [x] 강의 듣기
</code></pre>
<p>👉 <strong>결과</strong></p>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> 운동 하기</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" checked="true" disabled=""> 강의 듣기</li>
</ul>
<h6 id="참고"><a href="https://velog.io/@yuuuye/velog-%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4MarkDown-%EC%9E%91%EC%84%B1%EB%B2%95">참고</a></h6>

