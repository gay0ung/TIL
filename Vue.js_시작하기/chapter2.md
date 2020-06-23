---


---

<h2 id="🟢-section2--instance인스턴스">🟢 section2 : instance(인스턴스)</h2>
<blockquote>
<p><a href="https://joshua1988.github.io/vue-camp/textbook.html">인스턴스 정의</a></p>
</blockquote>
<pre><code>new Vue()
</code></pre>
<p>: Vue객체 안에 있는 api를 사용할수 있다.</p>
<h3 id="생성자-함수">생성자 함수</h3>
<blockquote>
<p><a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Obsolete_Pages/Core_JavaScript_1.5_Guide/Creating_New_Objects/Using_a_Constructor_Function">생성자 함수란?</a><br>
<a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor">property 란?</a></p>
</blockquote>
<h3 id="인스턴스-옵션">인스턴스 옵션</h3>
<pre><code> new Vue({
     el: ,
     template: ,
     data: ,
     methods: ,
     created: ,
     watch: ,
 })
</code></pre>
<ul>
<li><strong>el</strong><br>
: 인스턴스가 그려지는 화면의 시작점(특정 HTML태그)</li>
<li><strong>template</strong><br>
: 화면에 표시할 요소 (HTML, CSS등)</li>
<li><strong>data</strong><br>
: 뷰의 반응성(Reactivity)가 반영된 데이터 속성</li>
<li><strong>methods</strong><br>
: 화면의 동작과 이벤트 로직을 제어하는 메서드</li>
<li><strong>created</strong><br>
: 뷰의 라이프 사이클과 관련된 속성</li>
<li><strong>watch</strong><br>
: data에서 정의한 속성이 변화했을 때 추가 동작을 수행할 수 있게 정의하는 속성</li>
</ul>
<blockquote>
<p><a href="https://github.com/gay0ung/vue_study/blob/master/2.VUE-BEGINNERS_inflearn/playground/instance.html">실습결과물</a></p>
</blockquote>

