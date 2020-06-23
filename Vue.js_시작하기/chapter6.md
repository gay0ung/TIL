---


---

<h2 id="🟢section6--라우터">🟢section6 :	라우터</h2>
<h3 id="뷰라우터란">뷰라우터란?</h3>
<p><a href="https://router.vuejs.org/kr/installation.html">router설치하기</a></p>
<h3 id="router-view">router view</h3>
<blockquote>
<p>HTML</p>
</blockquote>
<pre class=" language-html"><code class="prism  language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>div</span> <span class="token attr-name">id</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>app<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>h1</span><span class="token punctuation">&gt;</span></span>Hello App!<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>h1</span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>p</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>router-link</span> <span class="token attr-name">to</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>/foo<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>Go to Foo<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>router-link</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>router-link</span> <span class="token attr-name">to</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>/bar<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>Go to Bar<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>router-link</span><span class="token punctuation">&gt;</span></span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>p</span><span class="token punctuation">&gt;</span></span>
  <span class="token comment">&lt;!-- 라우트 아울렛 --&gt;</span>
  <span class="token comment">&lt;!-- 현재 라우트에 맞는 컴포넌트가 렌더링됩니다. --&gt;</span>
  <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>router-view</span><span class="token punctuation">&gt;</span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>router-view</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>div</span><span class="token punctuation">&gt;</span></span>
</code></pre>
<blockquote>
<p><em>JavaScript</em></p>
</blockquote>
<p>◾ 0. 모듈 시스템 (예: vue-cli)을 이용하고 있다면, Vue와 Vue 라우터를 import 한다. 그다음 <code>Vue.use(VueRouter)</code>를 호출한다.</p>
<p>1.라우트 컴포넌트를 정의<br>
▪ 아래 내용들은 다른 파일로부터 가져올 수 있다.</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">const</span> Foo <span class="token operator">=</span> <span class="token punctuation">{</span> template<span class="token punctuation">:</span> <span class="token string">'&lt;div&gt;foo&lt;/div&gt;'</span> <span class="token punctuation">}</span>
<span class="token keyword">const</span> Bar <span class="token operator">=</span> <span class="token punctuation">{</span> template<span class="token punctuation">:</span> <span class="token string">'&lt;div&gt;bar&lt;/div&gt;'</span> <span class="token punctuation">}</span>
</code></pre>
<p>2.라우트를 정의<br>
▪ 각 라우트는 반드시 컴포넌트와 매핑되어야 한다<br>
▪ "component"는 <code>Vue.extend()</code>를 통해 만들어진 실제 컴포넌트 생성자이거나 컴포넌트 옵션 객체</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">const</span> routes <span class="token operator">=</span> <span class="token punctuation">[</span>
  <span class="token punctuation">{</span> path<span class="token punctuation">:</span> <span class="token string">'/foo'</span><span class="token punctuation">,</span> component<span class="token punctuation">:</span> Foo <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span> path<span class="token punctuation">:</span> <span class="token string">'/bar'</span><span class="token punctuation">,</span> component<span class="token punctuation">:</span> Bar <span class="token punctuation">}</span>
<span class="token punctuation">]</span>
</code></pre>
<p>3.<code>routes</code> 옵션과 함께 router 인스턴스를 만든다.<br>
▪ 추가 옵션을 여기서 전달.</p>
<pre><code>const router = new VueRouter({
  routes // `routes: routes`의 줄임
})
</code></pre>
<p>4.루트 인스턴스를 만들고 mount 한다.<br>
▪ router와 router 옵션을 전체 앱에 주입…</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">const</span> app <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">Vue</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
      router
 <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">.</span><span class="token function">$mount</span><span class="token punctuation">(</span><span class="token string">'#app'</span><span class="token punctuation">)</span>    
</code></pre>
<p>✔ 라우터를 주입하였으므로 <code>this$router</code>와 현재 라우트를 <code>this.$route</code>로 접근할수 있다. <a href="https://router.vuejs.org/kr/guide/#html">(참고자료)</a></p>
<h3 id="router-link">router-link</h3>
<pre class=" language-html"><code class="prism  language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>p</span><span class="token punctuation">&gt;</span></span>
	<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>router-link</span> <span class="token attr-name">to</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>/foo<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>Go to Foo<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>router-link</span><span class="token punctuation">&gt;</span></span>
    <span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>router-link</span> <span class="token attr-name">to</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>/bar<span class="token punctuation">"</span></span><span class="token punctuation">&gt;</span></span>Go to Bar<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>router-link</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>p</span><span class="token punctuation">&gt;</span></span>
</code></pre>
<ul>
<li>구체적인 속성은 <code>to</code> prop을 이용합니다</li>
<li>기본적으로 <code>&lt;router-link&gt;</code>는 <code>&lt;a&gt;</code> 태그로 렌더링됩니다</li>
<li>페이지 이동을 위한 링크 태그 이다.</li>
</ul>
<h3 id="라우더-네비게이션-가드">라우더 네비게이션 가드</h3>
<blockquote>
<p>사용자의 인증 정보가 없으면 특정 페이지에 접근하지 못하게 할때 사용하는 기술.</p>
</blockquote>
<p><strong>네비게이션 가드의 종류</strong></p>
<ul>
<li>어플리케이션 전역에 동작하는 <em>전역가드</em></li>
<li>특정 URL에서만 동작하는 <em>라우터 가드</em></li>
<li>라우터 컴포넌트 안에 정의하는 <em>컴포넌트 가드</em></li>
</ul>
<p><strong>전역가드</strong><br>
라우터 인스턴스를 참조하는 객체</p>
<p>◾ 라우터 인스턴스 생성</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">var</span> router <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">VuewRouter</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<p>◾ API호출</p>
<pre class=" language-js"><code class="prism  language-js">router<span class="token punctuation">.</span><span class="token function">beforeEach</span><span class="token punctuation">(</span><span class="token keyword">function</span><span class="token punctuation">(</span>to<span class="token punctuation">,</span> <span class="token keyword">from</span><span class="token punctuation">,</span> next<span class="token punctuation">)</span><span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<blockquote>
<ul>
<li>to : 이동할 url</li>
<li>from: 현재 url</li>
<li>next: to에서 지정한 url로 이동하기 위해 꼭 호출해야 하는 함수.</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li><code>router.beforeEach()</code> 를 호출하고 나면 모든 라우팅이 대기 상태</li>
<li>url로 라우팅 하기 위해서는 next()를 호출해줘야 한다.</li>
</ul>
</blockquote>
<p><a href="https://joshua1988.github.io/web-development/vuejs/vue-router-navigation-guards/">navigation guard</a></p>
<h3 id="라우터-가드">라우터 가드</h3>
<p>특정 라우팅에 대해 가드 설정</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">var</span> router <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">VueRouter</span><span class="token punctuation">(</span><span class="token punctuation">{</span>
  routes<span class="token punctuation">:</span> <span class="token punctuation">[</span>
    <span class="token punctuation">{</span>
      path<span class="token punctuation">:</span> <span class="token string">'/login'</span><span class="token punctuation">,</span>
      component<span class="token punctuation">:</span> Login<span class="token punctuation">,</span>
      beforeEnter<span class="token punctuation">:</span> <span class="token keyword">function</span><span class="token punctuation">(</span>to<span class="token punctuation">,</span> <span class="token keyword">from</span><span class="token punctuation">,</span> next<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        <span class="token comment">// 인증 값 검증 로직 추가</span>
      <span class="token punctuation">}</span>
    <span class="token punctuation">}</span>
  <span class="token punctuation">]</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span>
</code></pre>
<h3 id="컴포넌트-가드">컴포넌트 가드</h3>
<p>라우터로 지정된 특정 컴포넌트에서 가드 설정</p>
<pre class=" language-js"><code class="prism  language-js"><span class="token keyword">const</span> Login <span class="token operator">=</span> <span class="token punctuation">{</span>
  template<span class="token punctuation">:</span> <span class="token string">'&lt;p&gt;Login Component&lt;/p&gt;'</span><span class="token punctuation">,</span>
  <span class="token function">beforeRouteEnter</span> <span class="token punctuation">(</span>to<span class="token punctuation">,</span> <span class="token keyword">from</span><span class="token punctuation">,</span> next<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment">// Login 컴포넌트가 화면에 표시되기 전에 수행될 로직</span>
    <span class="token comment">// Login 컴포넌트는 아직 생성되지 않은 시점</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token function">beforeRouteUpdate</span> <span class="token punctuation">(</span>to<span class="token punctuation">,</span> <span class="token keyword">from</span><span class="token punctuation">,</span> next<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment">// 화면에 표시된 컴포넌트가 변경될 때 수행될 로직</span>
    <span class="token comment">// `this`로 Login 컴포넌트를 접근할 수 있음</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token function">beforeRouteLeave</span> <span class="token punctuation">(</span>to<span class="token punctuation">,</span> <span class="token keyword">from</span><span class="token punctuation">,</span> next<span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token comment">// Login 컴포넌트를 화면에 표시한 url 값이 변경되기 직전의 로직</span>
    <span class="token comment">// `this`로 Login 컴포넌트를 접근할 수 있음</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span>
</code></pre>
<hr>
<p><a href="https://github.com/gay0ung/vue_study/blob/master/2.VUE-BEGINNERS_inflearn/playground/router.html">👏 실습결과물</a></p>

