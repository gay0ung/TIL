---


---

<h3 id="chapter7--브랜치-생성-및-조작하기">chapter7 : 브랜치 생성 및 조작하기</h3>
<h2 id="branch-생성하기"><strong>1. branch 생성하기</strong></h2>
<p><a href="https://learngitbranching.js.org/?locale=ko">게임으로배우는 git</a></p>
<p><img src="https://ifh.cc/g/kLFRSM.jpg" alt="enter image description here"></p>
<ol>
<li>커밋하면 커밋 객체가 생긴다. 커밋 객체에는 부모 커밋에 대한 참조와 실제 커밋을 구성하는 파일 객체가 들어 있다.</li>
<li>브랜치는 논리적으로는 어떤 커밋과 그 조상들을 묶어서 뜻하지만, 사실은 단순히 커밋 객체 하나를 가리킬 뿐이다. 앞의 그림에서 [master] 브랜치는 정확하게 C3 커밋 객체를, [featurel]브랜치는 C5 커밋 객체 하나만을 가르킨다.</li>
</ol>
<h3 id="브랜치는-언제-사용">브랜치는 언제 사용?</h3>
<ul>
<li>
<p><strong>새로운 기능 추가</strong><br>
: [master] 브랜치에는 정상적으로 동작하는 안정적인 버전의 프로젝트가 저장되어 있기 때문에 새로운 기능을 추가할 때  [master] 브랜치의 최신 커밋으로 부터 브랜치를 생성해서 개발한다.<br>
(이때는 개발 코드 리뷰, 테스트 까지 모두 완료해서 이상이 없으면[master]브랜치로 병합한다.)</p>
</li>
<li>
<p><strong>버그 수정</strong><br>
: 버그 발생시 [master]브랜치로부터 새로운 브랜치를 생성해서 작업한다. 이때 브랜치 이름은 <em>hotFix</em>또는 <em>bugFix</em> 와 같은 이름을 사용한다</p>
<p>: 버그 수정이 끝나면 당연히 [master]브랜치로 병합한다.<br>
(이경우, 이후에 새로 개발한 내용을 다시 [master]브랜치에 병합할 때 버그 수정으로 인해 충돌이 생길 수 있기 때문에 주의해야 한다.)</p>
</li>
<li>
<p><strong>병합과 리베이스 테스트</strong><br>
: 임시 브랜치를 만들어서 병합과 리베이스 테스트를 해보면 편리하다.<br>
(잘못 되었을 경우 브랜치를 삭제해 버리면 된다.)</p>
</li>
<li>
<p><strong>이전 코드 개선</strong><br>
: 새로 브랜치를 만들어 이전 코드는 과감하게 삭제하고 새 코드를 작성하는것.<br>
(다른 브랜치의 이전 커밋에는 잘 돌아가는 코드가 여전히 남아있기 때문에 걱정 안 해도 된다)</p>
</li>
<li>
<p><strong>특정커밋으로 돌아가고 싶을때</strong><br>
: 일반적으로 이미 저장되어 있는 특정 커밋을 돌아가고 싶을때 <em>hard reset &amp; revert</em>를 사용한다.<br>
( reset의 경우 커밋이 없어질수 있기 때문에 추천하지 않는다)</p>
<p>: 브랜치를 새로 만들어 작업하고, 이후 리베이스나 병합을 사용하는 편이 안전하다.</p>
</li>
</ul>
<h3 id="브랜치-생성하기">브랜치 생성하기</h3>
<pre><code>$ git branch [-v]
</code></pre>
<p>▪ 로컬 저장소의 브랜치 목록을 보는 명령<br>
▪  -v 옵션을 사용하면 마지막 커밋도 함께 표시된다.<br>
▪  표시된 브랜치 중에서 이름 왼쪽에 *가 붙으면 HEAD브랜치이다.</p>
<pre><code>$ git branch [-f] &lt;브랜치 이름&gt; [커밋체크섬]
</code></pre>
<p>▪ 새로운 브랜치를 생성한다<br>
▪ 커밋체크섬 값을 주지 않으면 HEAD로 부터 브랜치를 생성한다.<br>
▪ 이미 있는 브랜치를 다른 커밋으로 옮기고 싶을 때는  -f옵션을 줘야 한다.</p>
<pre><code>$ git branch -r[-v]
</code></pre>
<p>▪ 원격 저장소에 있는 브랜치를 보고 싶을 때 사용한다.<br>
▪ -v옵션을 추가하여 커밋 요약도 볼 수 있다.</p>
<pre><code>$ git checkout &lt;브랜치이름&gt;
</code></pre>
<p>▪ 특정 브랜치로 체크아웃할 때 사용한다.<br>
▪ 브랜치 이름 대신 커밋 체크섬을 쓸수 있다.</p>
<pre><code>$ git checkout -b &lt;브랜치이름&gt; &lt;커밋 체크섬&gt;
</code></pre>
<p>▪ 특정 커밋에서 브랜치르 ㄹ새로 생성하고 동시에 체크아웃까지 한다.<br>
▪ 두 명령을 하나로 합친 명령이기 때문에 간결해서 자주 사용</p>
<pre><code>$ git mearge &lt;대상 브랜치&gt;
</code></pre>
<p>▪ 현재 브랜치와 대상 브랜치를 병합할 때 사용<br>
▪ 병합 커밋(merge commit) 이 새로 생기는 경우가 많다.</p>
<pre><code>$ git rebase &lt;대상 브랜치&gt;
</code></pre>
<p>▪ 내 브랜치의 커밋들을 대상 브랜치에 재배치시킨다.<br>
▪ 히스토리가 깔끔해 져서 자주사용하지만 조심해야 한다.</p>
<pre><code>$ git branch -d
</code></pre>
<p>▪ 특정 브랜치를 삭제 할때 사용<br>
▪ HEAD브랜치나 병합이 되지 않은 브랜치는 삭제할수 없다!</p>
<pre><code>$ git branch -D
</code></pre>
<p>▪ 브랜치를 강제로 삭제하는 명령이다<br>
(조심하게 사용해야한다.)</p>
<p>◼<strong>브랜치 만들기</strong><br>
<img src="https://ifh.cc/g/mpqLd9.jpg" alt="enter image description here"></p>
<blockquote>
<p><strong>HEAD에 대해 반드시 기억할점 ❗</strong><br>
-현재 작업중인 브랜치를 가리킨다.<br>
-브랜치는 커밋을 가리키므로 HEAD도 커밋을 가리킨다<br>
-결국 HEAD는 현재 작업중인 브랜치의 최근 커밋을 가리킨다.</p>
</blockquote>
<blockquote>
<p><strong>revert를 사용해 커밋을 되돌려야 하는경우</strong></p>
<p><em>C1 ← F1 ← C2 ← F2 ← C3(master)</em></p>
<dl>
<dt>❔ 원하는바</dt>
<dd>[master]브랜치에 있는 기능 하나를 취소하고 싶다</dd>
<dt>해석</dt>
<dd>여러개의 커밋(F1, F2)으로 나누어져 있고 사이사이 (C2,C3)포함되어 있다.</dd>
<dt>해결</dt>
<dd>git revert를 실행할 때는 최신 커밋부터 취소하는게 좋다.<br>
<code>$git revert F2</code><br>
<code>$git revert F1</code><br>
<em>C1 ← F1 ← C2 ← F2 ← C3 ← RF2 ← RF1(master)</em></dd>
</dl>
<ul>
<li>F2,F1을 취소하는 커밋(RF2 ,RF1)를 각각 만들어 낸다.</li>
<li>이전히스토리를 변경하지 않고도 깔끔하게 히스토리 중간의 여러 커밋 내용을 작업 이전 상태로 되돌릴수 있다.</li>
</ul>
</blockquote>
<h2 id="체크아웃-병합-되돌리기-태그"><strong>2. 체크아웃, 병합, 되돌리기, 태그</strong></h2>
<p>◼<strong>브랜치 만들기</strong><br>
<img src="https://ifh.cc/g/yJV4w3.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/iDzCWp.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/gnXPhJ.jpg" alt="enter image description here"></p>
<blockquote>
<p><strong>git checkout&lt;커밋체크섬&gt;을 하면 어떤일이 벌어질까?</strong></p>
<ul>
<li>HEAD와 브랜치가 분리되는 Detached HEAD상황이 벌어진다.</li>
<li>이 상황에서 도 여전히 커밋을 생성할 수 있지만 다른 브랜치로 체크아웃하는 순간 Detached HEAD의 커밋들이 다사라져서 안보이게 된다. (🔅실수로 이런상황이 벌어졌을때 <code>$git reflog</code> 명령으로 복수 할수 있지만 권장하진 않는다)</li>
</ul>
</blockquote>
<p><strong>커밋 전후</strong><br>
<img src="https://ifh.cc/g/rdHoWQ.jpg" alt="enter image description here"></p>
<blockquote>
<p><strong>새로운 커밋을 생성하면 새로 커밋을 생성하면</strong></p>
<ul>
<li>새로운 커밋을 생성하면 새로 커밋을 생성하면 그 커밋의 부모는 언제나 이전 HEAD커밋이다.</li>
<li>커밋이 생성되면 HEAD는 새로운 커밋으로 갱신된다.</li>
<li>HEAD가 가리키는 브랜치도 HEAD와 함께 새로운 커밋을 가리킨다.</li>
</ul>
</blockquote>
<h3 id="cli를-이용한-빨리-감기-병합">CLI를 이용한 빨리 감기 병합</h3>
<p><img src="https://ifh.cc/g/TpYerM.jpg" alt="enter image description here"></p>
<p>◼<strong>커밋 후 빨리 감기 병합(fast-forward)</strong><br>
<img src="https://ifh.cc/g/xExh5Z.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/dXVwIg.jpg" alt="enter image description here"></p>
<h3 id="reset---hard로-브랜치-되돌리기">reset --hard로 브랜치 되돌리기</h3>
<p><strong>reset</strong> : 현재 브랜치를 특정 커밋으로 되돌릴 때 사용한다.</p>
<pre><code>$ git reset --hard &lt;이동할 커밋 체크섬&gt;
</code></pre>
<blockquote>
<p>-현재 브랜치를 지정한 커밋으로 옮긴다.<br>
-작업 폴더의 내용도 함께 변경된다.<br>
-가장 많이 사용된다.<br>
<strong>‼ 체크섬을 간단하게 확인하는 법</strong></p>
<ul>
<li>
<p><code>HEAD~&lt;숫자&gt;</code><br>
: HEAD~ 은 헤드의 부모 커밋,<br>
: HEAD~2 는 헤드의 할아버지 커밋<br>
: HEAD~n 은 n번째 위쪽 조상이라는 뜻.</p>
</li>
<li>
<p><code>HEAD^&lt;숫자&gt;</code><br>
: HEAD^ 는 부모 커밋<br>
: HEAD^2는 두번째 부모를 가르킨다.<br>
: <mark>병합 커밋처럼 부모가 둘 이상인 커밋에서만 의미가 있다.</mark></p>
</li>
</ul>
</blockquote>
<p>◼<strong>현재 브랜치를 두 단계 이전으로 되돌리기</strong><br>
<img src="https://ifh.cc/g/hWBPD5.jpg" alt="enter image description here"></p>
<blockquote>
<p><code>$ reset --hard</code> 명령이 <code>$ checkout</code> 명령과 비슷하네?</p>
<p><code>$ git checkout HEAD~2</code> 를 입력하면 [master]브랜치는 그자리에 있고 HEAD만 옮겨진다.</p>
<p><strong>[master]브랜치와 HEAD를 연결하려면 어떻게 할까?</strong><br>
<code>$ git checkout HEAD~2</code><br>
<code>$ git branch -f master</code><br>
<code>$ git checkout master</code><br>
: reset --hard명령은 위의 세 명령을 한번에 수행하는 명령어 이다.</p>
</blockquote>
<p>◼<strong>rebase, push, branch제거</strong><br>
<img src="https://ifh.cc/g/2Ho9fH.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/QRgSy2.jpg" alt="enter image description here"></p>
<h3 id="배포버전에-태깅하기">배포버전에 태깅하기</h3>
<pre><code>$ git tab -a -m &lt;간단한 메세지&gt; &lt;태그이름&gt; [브랜치 또는 체크섬]
</code></pre>
<p>▪ -a로 주석 있는(annotated)태그를 생성한다.<br>
▪  메시지와 태그 이름은 필수이며 브랜치 이름을 생량하면 HEAD에 태그를 생성한다.</p>
<pre><code>$ git push &lt;원격저장소 별명&gt; &lt;태그이름&gt;
</code></pre>
<p>▪  원격 저장소에 태그를 업로드 한다.</p>
<p>◼<strong>태그 작성</strong><br>
<img src="https://ifh.cc/g/0nF0Pv.jpg" alt="enter image description here"></p>
<h2 id="mearge-3-way-병합하기"><strong>3. mearge (3-way 병합하기)</strong></h2>
<h3 id="긴급한-버그-처리-시나리오">긴급한 버그 처리 시나리오</h3>
<blockquote>
<ol>
<li>(옵션)오류가 없는 버전 (주로 Tag가 있는 커밋)으로 롤백</li>
<li>[master]브랜치로부터 [hotfix]브랜치 생성</li>
<li>빠르게 소스 코드 수정/테스트완료</li>
<li>[master]브랜치로 병합(Fast-forward)및 배포</li>
<li>개발 중인 브랜치에도 병합(충돌 발생 가능성이 높음)</li>
</ol>
</blockquote>
<p>◼<strong>새로운 브랜치 및 커밋 생성</strong><br>
<img src="https://ifh.cc/g/sah4H6.jpg" alt="enter image description here"></p>
<pre><code>$ git checkout -b feature1 (#feature1브랜치 생성 및 체크아웃)
</code></pre>
<p><img src="https://ifh.cc/g/Q2H6hT.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/Va2Fq5.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/B6Lq8l.jpg" alt="enter image description here"></p>
<blockquote>
<p>이미 커밋한 상태에서 장애가 발생.</p>
</blockquote>
<p>◼<strong>hotfilx 브랜치 생성, 커밋, master에 병합</strong><br>
<img src="https://ifh.cc/g/WGddtN.jpg" alt="enter image description here"></p>
<blockquote>
<ol>
<li>master 브랜치에 hotfilx브랜치를 만들었다.</li>
<li>버그를 고친후 커밋</li>
<li>hotfix브랜치를 master브랜치에 병합한다.</li>
</ol>
</blockquote>
<p><img src="https://ifh.cc/g/j5Wycu.jpg" alt="enter image description here"></p>
<blockquote>
<p><strong>충돌이 발생한 file1.txt파일</strong></p>

<table>
<thead>
<tr>
<th>master 브랜치의 file1.txt</th>
<th>feature1 브랜치의 file1.txt</th>
</tr>
</thead>
<tbody>
<tr>
<td>hello git</td>
<td>hello git</td>
</tr>
<tr>
<td>second</td>
<td>second</td>
</tr>
<tr>
<td>third -my branch</td>
<td>third -my branch</td>
</tr>
<tr>
<td>fourth</td>
<td>fourth</td>
</tr>
<tr>
<td>some hot fix</td>
<td>신규기능</td>
</tr>
</tbody>
</table></blockquote>
<blockquote>
<p>고의적으로 두 브랜치 모두 file1.txt를 수정했기에 충돌이 일어남.</p>
</blockquote>
<p>◼<strong>병합 및 충돌 해결하기 1</strong><br>
<img src="https://ifh.cc/g/cSyDTv.jpg" alt="enter image description here"></p>
<blockquote>
<p><code>$ git merge master</code> 명령이 충돌로 인해 실패<br>
<code>$ git status</code> 를 실행해 충돌 대상을 확인할수 있음<br>
(<code>$ git merge --abort</code> 명령을 통해 merge를 취소할수도 있다)</p>
<p>vs code로 파일을 열어 <em>두변경 사항 모두 수락</em> 항목을 클릭해주면 깔끔하게 정리된다. <img src="https://ifh.cc/g/JZTAcF.jpg" alt="enter imagedescription here"></p>
</blockquote>
<p>◼<strong>병합 및 충돌 해결하기2</strong><br>
<img src="https://ifh.cc/g/LRyTAs.jpg" alt="enter image description here"></p>
<blockquote>
<ul>
<li><code>$ git add</code> 및 <code>$ git status</code>를 수행하면 충돌한 파일의 수정을 완료한 후에 <code>$ git commit</code>명령을 수행하면 된다는 것을 알 수 있다.</li>
<li><code>$ git commit</code>으로 충돌난 3 way병합을 마무리 한다.</li>
</ul>
</blockquote>
<p><img src="https://ifh.cc/g/rWPCHk.jpg" alt="enter image description here"></p>
<h2 id="rebase-리베이스"><strong>4. rebase (리베이스)</strong></h2>
<h3 id="rebase-사용하기">rebase 사용하기</h3>
<blockquote>
<p><strong>3-way병합</strong>은 커밋이 생성되기 때문에 트리가 다소 지저분할 수 있다.<br>
<mark>reabase</mark>로 트리를 깔끔하게 할수 있다.<br>
<img src="https://ifh.cc/g/uE6zmA.jpg" alt="enter image description here"></p>
<p><code>$ git rebase master</code> 를 실행한뒤 c4,c5와 c4’,c5’ 커밋은 각각 다른 커밋이다.</p>
</blockquote>
<p>◼<strong>reset --hard및 rebase시도</strong><br>
<img src="https://ifh.cc/g/gOQbVX.jpg" alt="enter image description here"></p>
<blockquote>
<p><code>$ git reset --hard HEAD~</code> 명령으로 커밋을 한 단계 이전으로 되돌렸다.(병합커밋전 단계로 돌리고 싶어서)</p>
<p><em>하지만 충돌로 있해 rebase는 실패한다.</em></p>
</blockquote>
<p>◼<strong>충돌 해결 및 rebase이어서 하기</strong><br>
<img src="https://ifh.cc/g/F2xTHY.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/rJeck2.jpg" alt="enter image description here"></p>
<h3 id="way-병합과-rebase">3-way 병합과 rebase</h3>

<table>
<thead>
<tr>
<th></th>
<th>3-way</th>
<th>rebase</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>특징</strong></td>
<td>머지 커밋 생성</td>
<td>현재 커밋들을 수정하면 대상 브랜치 위로 재배치함.</td>
</tr>
<tr>
<td><strong>장점</strong></td>
<td>한 번만 충돌 발생</td>
<td>깔끔한 히스토리</td>
</tr>
<tr>
<td><strong>단점</strong></td>
<td>트리가 약간 지저분해짐</td>
<td>여러번 충돌이 발생할 수 있음</td>
</tr>
</tbody>
</table><h3 id="유용한-rebase의-사용법뻗어나온-가지-없애기">유용한 rebase의 사용법:뻗어나온 가지 없애기</h3>
<blockquote>
<p>(이부분 다시 해봐야 겠다 결과물이 전부 다르다)</p>
</blockquote>
<p>◼<strong>보통커밋 만들기</strong><br>
<img src="https://ifh.cc/g/OxTXPA.jpg" alt="enter image description here"></p>
<p>◼<strong>가지 커밋 만들기</strong><br>
<img src="https://ifh.cc/g/XHjWtw.jpg" alt="enter image description here"></p>
<blockquote>
<p><code>$ git reset --hard HEAD~</code> 를 이용해 한단계 되돌렸다.</p>
</blockquote>
<p>◼<strong>git pull 수행결과</strong><br>
<img src="https://ifh.cc/g/pMCTS7.jpg" alt="enter image description here"></p>
<blockquote>
<p>🔅난 결과물이 다른것 같다… 어디서 부터 잘못됐지…?</p>
</blockquote>
<p>◼<strong>rebase로 가지 없애기</strong><br>
<img src="https://ifh.cc/g/KwlJ3i.jpg" alt="enter image description here"></p>
<blockquote>
<p>🔅이것또한 결과물이 다르다.</p>
</blockquote>
<h3 id="rebase-주의사항">rebase 주의사항</h3>
<p>‼ 원격 저장소에 푸시한 브랜치는 rebase하지 않는다.!</p>
<h3 id="임시-브랜치-사용하기">임시 브랜치 사용하기</h3>
<p>◼<strong>임시 브랜치 생성 사용 및 삭제</strong><br>
<img src="https://ifh.cc/g/Xsj3Ic.jpg" alt="enter image description here"></p>
<blockquote>
<p>🔅이것또한 결과물이 다르다.</p>
</blockquote>

