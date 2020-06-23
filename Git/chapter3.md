---


---

<h2 id="chapter3--branch">chapter3 : Branch</h2>
<dl>
<dt>[HEAD]태그 : branch 또는 commit을 가리키는 포인터 이다.</dt>
<dd>브랜치 사이를 마음대로 움직일수 있다.</dd>
</dl>
<p><strong>협업할때 규칙</strong></p>
<ol>
<li>master 브랜치에는 직접 커밋을 올리지 않는다(동시에 작업하다 꼬일수 있으므로)</li>
<li>기능 개발을 하기 전에 master 브랜치를 기준으로 새로운 브랜치를 만든다.</li>
<li>이 브랜치 이름은[feature/기능이름]형식으로 하고 한 명만 커밋을 올린다.</li>
<li>[feature/기능이름]브랜치에서 기능 개발이 끝나면 [master]브랜치에 이를 합친다.</li>
</ol>
<p>&lt;여러개의 브랜치를 합치는 과정&gt;<br>
merge머지 (병합)</p>
<p>&lt;브랜치를 합치는 예의바른 방법&gt;<br>
:Pullrequest<br>
: 승인이 있을시에만 병합가능하게 하는 기능.</p>
<dl>
<dt>&lt;프로그램출시&gt;</dt>
<dd>release</dd>
<dd>tag-&gt;특정  커밋에 포스트잇처럼 붙인다</dd>
</dl>

