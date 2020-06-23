---


---

<h2 id="🟢section3--component컴포넌트">🟢section3 : component(컴포넌트)</h2>
<h3 id="뷰-컴포넌트-">뷰 컴포넌트 <a href="https://joshua1988.github.io/vue-camp/vue/components.html">?</a></h3>
<p><img src="https://ifh.cc/g/8BHfB0.jpg" alt="enter image description here"></p>
<p>▪ 화면 영역을 구분하여 개발 할 수 있는 뷰의 기능<br>
▪ 컴포넌트 기반으로 화면을 개발하게 되면 코드의 재사용성이 올라가고 빠르게 화면을 제작 할 수 있다.</p>
<p>전역 컴포넌트</p>
<pre><code>Vue.component('컴포넌트 이름',{컴포넌트 내용})
</code></pre>
<p>지역 컴포넌트</p>
<pre><code>new Vue({
    components: {
	    '컴포넌트 이름': 컴포넌트 내용
    }
})
</code></pre>
<blockquote>
<p><a href="https://github.com/gay0ung/vue_study/blob/master/2.VUE-BEGINNERS_inflearn/playground/component.html">실습결과물</a></p>
</blockquote>

