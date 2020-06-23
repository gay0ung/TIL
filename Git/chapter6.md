---


---

<h3 id="chapter6--clicommend-line-interface">chapter6 : CLI(Commend Line Interface)</h3>
<h2 id="cli"><strong>1. CLI</strong></h2>
<p><strong>GUI환경</strong><br>
다양한 정보(텍스트,이미지, 버튼등)가 화면에 표시됨 → 화면을 보며 할일을 결정 → 마우스와 키보드로 명령<br>
(이과정을 계속해서 반복한다.)</p>
<ul>
<li><strong>CLI환경</strong><br>
프롬프트에 최소한의 정보(C:.$ 등)가 표시됨 → 키보드로 명령 입력 → 명령 처리 결과가 텍스트로 화면에 표시됨</li>
</ul>
<hr>
<p><strong>◼ CLI명령 실행 중 발생하는 에러 메세지</strong><br>
<img src="https://ifh.cc/g/fhEHVh.png" alt="enter image description here"></p>
<h2 id="git-bash"><strong>2. Git Bash</strong></h2>
<p><strong>◼ Prompt : 프롬프트</strong><br>
<img src="https://ifh.cc/g/wZBWvx.jpg" alt="enter image description here"><br>
: $기호와 표시된 경로 같은것</p>
<hr>
<h3 id="git-bash-기본명령어">Git Bash 기본명령어</h3>
<pre><code>$ pwd
</code></pre>
<p>현재 폴더의 위치 확인</p>
<pre><code>$ ls -a
</code></pre>
<p>현재 폴더의 파일 목록을 확인.<br>
-a 옵션을 이용해 숨김 파일도 볼수 있다.</p>
<pre><code>$ cd
</code></pre>
<p>홈 폴더로 이동<br>
홈 폴더는 사용자 이름과 폴더명이 같고 내 문서 폴더의 상위 폴더이다.</p>
<pre><code>$ cd&lt;폴더이름&gt;
</code></pre>
<p>특정 위치의 디렉토리로 이동</p>
<pre><code>$ cd ../ 
</code></pre>
<p>현재 폴더의 상위 폴더로 이동</p>
<pre><code>$ mkdir &lt;새폴더이름&gt;
</code></pre>
<p>현재 폴더의 아래에 새로운 폴더를 만든다.</p>
<pre><code>$ echo "Hello Git"
</code></pre>
<p>화면에  " "안의 문장인 " Hello Git"을 표시</p>
<pre><code>$ git status
</code></pre>
<p>Git 워킹트리의 상태를 보는 명령(매우자주 사용)<br>
워킹트리가 아닌 폴더에서 실행하면 오류가 발생합니다.</p>
<pre><code>$ git status -s
</code></pre>
<p>git status 명령 보다 짧게 요약해서 상태를 보여주는 명령으로, 변경된 파일이 많을 때 유용합니다.</p>
<pre><code>$ git init
</code></pre>
<p>현재 폴더에 Git 저장소를 생성한다<br>
현재 폴더에는[.git]이라는 숨김 폴더가 생성되는데 사실 이 폴더가 로컬저장소 이다.</p>
<h3 id="git용어">Git용어</h3>

<table>
<thead>
<tr>
<th>용어</th>
<th>정의</th>
</tr>
</thead>
<tbody>
<tr>
<td>워킹트리</td>
<td>일반적인 작업이 일어나는 곳</td>
</tr>
<tr>
<td>로컬저장소</td>
<td>git폴더, 커밋은 여기에 들어있다.</td>
</tr>
<tr>
<td>작업폴더</td>
<td>워킹트리 + 로컬저장소</td>
</tr>
<tr>
<td>Git저장소</td>
<td>엄밀하게는 로컬저장소의미, 넒은 의미로는 작업 폴더를 의미</td>
</tr>
</tbody>
</table><blockquote>
<ul>
<li>워킹트리(working tree)<br>
: 워크트리, 워킹 디렉토리, 작업 디렉토리, 작업 폴더 모두 같은 뜻으로 사용.<br>
: 일반적으로 사용자가 파일과 하위 폴더를 만들고 작업 결과물을 저장하는 곳을 Git에서는 워킹트리라고 부른다.<br>
: 공식문서에는 워킹트리를  '커밋을 체크아웃하면 생성되는 파일과 디렠토리’로 정의하고 있다.	<br>
: 작업폴더에서[.git]폴더(로컬저장소)를 뺀 나머지 부분이 워킹트리</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li>로컬 저장소(local repository)<br>
: Git init 명령으로 생성되는[.git]폴더가 로컬저장소이다. 커밋, 커밋을 구성하는 객체, 스테이지가 모두 이 폴더에 저장된다.</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li>원격저장소(remote repository)<br>
: 로컬저장소를 업로드하는 곳<br>
: 우리가 사용하는 GitHub 저장소가 원격저장소 이다.</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li>Git 저장소<br>
: Git 명령으로 관리할 수 있는 폴더 전체를 일반적으로 Git 프로젝트 혹은 Git 저장소 라고 부른다.</li>
</ul>
</blockquote>
<h3 id="git-옵션설정하기">Git 옵션설정하기</h3>
<p>◾ 전역  : 현재 사용자를 위한 옵션<br>
◾ 지역 : Git 저장소에서만 유효한 옵션<br>
◾ 시스템 환경  : pc전체의 사용자를 위한옵션</p>
<blockquote>
<p>지역 &gt; 전역 &gt; 시스템</p>
</blockquote>
<pre><code>$git config --global &lt;옵션명&gt;
</code></pre>
<p>: 저장한 전역 옵션의 내용을 살펴 본다.</p>
<pre><code>$git config --global &lt;옵션명&gt; &lt;새로운 값&gt;
</code></pre>
<p>: 지정한 전역 옵션의 값을 새로 설정한다.</p>
<pre><code>$git config --global --unset &lt;옵션명&gt;
</code></pre>
<p>: 지정한 전역 옵션을 삭제 한다.</p>
<pre><code>$git config --local&lt;옵션명&gt;
</code></pre>
<p>: 지정한 지역 옵션의 값을 새로 설정 한다.</p>
<pre><code>$git config --local &lt;옵션명&gt; &lt;새로운 값&gt;
</code></pre>
<p>: 지정한 지역 옵션의 값을 새로 설정한다.</p>
<pre><code>$git config --local --unset &lt;옵션명&gt;
</code></pre>
<p>: 지정한 지역 옵션의 값을 삭제 한다.</p>
<pre><code>$git config -- system&lt;옵션명&gt;
</code></pre>
<p>: 지정한 시스텝 옵션의 내용을 살펴본다.</p>
<pre><code>$git config --system&lt;옵션명&gt; &lt;값&gt;
</code></pre>
<p>: 지정한 시스템 옵션의 값을 새로 설정한다.</p>
<pre><code>$git config --system --unset&lt;옵션명&gt; &lt;값&gt;
</code></pre>
<p>: 지정한 시스템 옵션의 값을 삭제한다.</p>
<pre><code>$git config --list
</code></pre>
<p>: 현재 프로젝트의 모든 옵션을 살펴본다.</p>
<p><strong>◼ username 변경하기</strong><br>
<img src="https://ifh.cc/g/PwTEeY.jpg" alt="enter image description here"></p>
<p><strong>◼ Git 기본 에디터 확인하기</strong><br>
<img src="https://ifh.cc/g/eQJASK.jpg" alt="enter image description here"></p>
<blockquote>
<p>git config --system core.editor부분 에서는 확인이 안됬다.<br>
global변수에는 확있이 되어있는데 그이유는 글로벌 옵션은 시스템 옵션보다 우선시 되므로 정상적으로 비주얼 스튜디오 코드가 실행된다.</p>
</blockquote>
<h2 id="기본-cli명령어"><strong>3. 기본 CLI명령어</strong></h2>
<pre><code>$ git add 파일1 파일2 ...
</code></pre>
<p>파일들을 스테이지에 추가한다<br>
새로 생성한 파일을 스테이지에 추가하고 싶다면 반드시 add 명령을 사용한다.</p>
<pre><code>$ git commit
</code></pre>
<p>스테이지에 있는 파일들을 커밋한다.</p>
<pre><code>$ git commit -a
</code></pre>
<p>add 명령을 생략하고 바로 커밋하고 싶을 때 사용<br>
변경된 파일과 삭제된 파일은 자동으로 스테이징되고 커밋된다.<br>
(❗ 주의할점 : untracked 파일은 커밋되지 않는다.)</p>
<pre><code>$ git push[-u] [원격저장소 별명] [브랜치 이름]
</code></pre>
<p>현재 브랜치에서 새로 생성한 커밋들을 원격저장소에 업로드한다.<br>
-u 옵션으로 브랜치의 업스트림을 등록할 수 있다. 한번 등록한 후에는 git push만 입력해도 된다.</p>
<pre><code>$ git pull
</code></pre>
<p>원격저장소의 변경사항을 워킹트리에 반영한다.<br>
git fetch + git merge 명령이다.</p>
<pre><code>$ git fetch [원격저장소 별명] [브랜치 이름]
</code></pre>
<p>원격 저장소의 브랜치와 커밋들을 로컬저장소와 동기화 한다.<br>
옵션을 생략 하면 모든 원격저장소에서 모든 브랜치를 가져온다.</p>
<pre><code>$ git merge 브랜치이름
</code></pre>
<p>저장한 브랜치의 커밋들을 현재 브랜치 및 워킹트리에 반영한다.</p>
<p><strong>◼ 간단한 텍스트 파일 생성하고 확인하기</strong><br>
<img src="https://ifh.cc/g/eJ5lB2.jpg" alt="enter image description here"></p>
<p><strong>◼ 생성한 파일 스테이지에 추가하기</strong><br>
<img src="https://ifh.cc/g/d97qEv.jpg" alt="enter image description here"></p>
<blockquote>
<p>file1.txt파일이 생성됬다.<br>
… : 한번에 여러파일 이름 지정할수 있다.</p>
</blockquote>
<p>스테이지 취소명령</p>
<pre><code>$git reset [파일명]...
</code></pre>
<p>스테이지 영역에 있는 파일들을 스테이지에서 내린다(<mark>언스테이징</mark>)<br>
워킹트리의 내용은 변경되지 않는다. 옵션을 생략할 경우 스테이지의 모든 변경사항을 초기화 한다.</p>
<blockquote>
<p><strong>reset options</strong></p>
<ul>
<li>soft</li>
<li>mixed</li>
<li>hard</li>
</ul>
</blockquote>
<p><strong>◼ 스테이지에서 파일 언스테이징 하기</strong><br>
<img src="https://ifh.cc/g/XovsS5.jpg" alt="enter image description here"></p>
<blockquote>
<p>🔴 -&gt;  언스테이징 되어 스테이지에서 내려간 상태<br>
<code>$ cat [파일명]</code><br>
-파일 내용이 변경 되었는지 확인한다.<br>
-결과: 파일의 내용은 그대로 두고 단지 언스테이징만을 한것을 알 수 있다.</p>
</blockquote>
<p><strong>◼ 첫번재 CLI 커밋</strong><br>
<img src="https://ifh.cc/g/7rTdw2.jpg" alt="enter image description here"></p>
<blockquote>
<p>-git coomit 을하면 vscode 프로그램이 열린다.<br>
-vscode 가 실행되면 코드의 첫줄과 둘째줄 사이는 반드시 한줄을 비워야 한다.<br>
-첫줄에는 작어버 내용의 요약, 다음줄에는 자세하게 작업 내용을 기록 한다.</p>
</blockquote>
<p><strong>◼ 커밋 확인해보기</strong><br>
<img src="https://ifh.cc/g/7OcRin.jpg" alt="enter image description here"></p>
<blockquote>
<p>앞의7자리 숫자 : 커밋 아이디</p>
</blockquote>
<h3 id="git-log의-옵션">git log의 옵션</h3>
<pre><code>$ git log
</code></pre>
<p>현재 브랜치의 커밋 이력을 보는 명령<br>
HEAD와 관련된 커밋들이 자세하게 나온다.</p>
<pre><code>$ git log -n&lt;숫지&gt;
</code></pre>
<p>전체 커밋 중에서 최신 n개의 커밋만 살펴본다<br>
아래의 다양한 옵션과 조합해서 사용할수 있다.</p>
<pre><code>$ git log --oneline --graph --decorate --all
</code></pre>
<p>-자주 사용하는 옵션 간결하게 내용을 보여준다.</p>
<ul>
<li><em>(-- 가 써지지 않았다 모든 옵션들을 참고해서 봐준다)</em></li>
<li>–oneline : 커밋 메세지를 한줄로 요약해서 보여준다. 생략하면 커밋 정보를 자세히 표시한다.</li>
<li>–graph : 커밋 옆에 브랜치의 흐름을 그래프로 보여준다. GUI와 유사한 모습으로 나온다.</li>
<li>–decorate: 원래는 --decorate=short 옵션을 의미한다. 브랜치와 태그 등의 참조를 간결히 표시한다.</li>
<li>–all: all 옵션이 없을 경우 HEAD와 관계없는 옵션은 보여주지 않는다.</li>
</ul>
<blockquote>
<p><code>$ git log --oneline</code><br>
간단히 커밋 해시와 제목만 보고 싶을때<br>
<code>$ git log --oneline -n5</code><br>
내 브랜치의 최신 커밋을 5개만 보고 싶을때 사용.</p>
</blockquote>
<blockquote>
<p><strong>좋은 커밋이란?</strong></p>
<ol>
<li>제목과 본문을 빈 줄로 분리한다</li>
<li>제목은 50자 이내로 쓴다</li>
<li>제목을 영어로 쓸경우 첫 글자는 대문자로 쓴다.</li>
<li>제목에는 마침표를 넣지 않는다.</li>
<li>제목을 영어로 쓸 경우 동사원형으로 시작한다</li>
<li>본문을 72자 단위로 줄바꿈한다</li>
<li>how 보다는 why,what 을 설명해준다.</li>
</ol>
</blockquote>
<h3 id="도움말-기능">도움말 기능</h3>
<pre><code>$ git help &lt;명령어&gt;
</code></pre>
<p>해당 명령어의 도움말을 표시한다<br>
도움말에는 명령의 의미와 세부적인 옵션들이 매우 자세하게 표시된다.</p>
<blockquote>
<p><code>$ git help status</code><br>
<code>$ git help commit</code><br>
<code>$ git help add</code></p>
</blockquote>
<h2 id="원격저장소-관련-cli-명령어">4. 원격저장소 관련 CLI 명령어</h2>
<h3 id="원격저장소-등록하는-cli-명령어">원격저장소 등록하는 cli 명령어</h3>
<pre><code>$ git remote add &lt;원격저장소이름&gt;&lt;원격주소&gt;
</code></pre>
<p>원격 저장소를 등록한다.<br>
원격 저장소는 여러 개 등록할 수 있지만 같은 별명의 원격저장소는 하나만 가질 수 있다. 통상 첫 번째 원격저장소를 orgin으로 지정한다.</p>
<pre><code>$ git remote -v
</code></pre>
<p>원격저장소 목록을 살펴 본다.</p>
<p><strong>◼ 원격저장소 등록 및 push</strong><br>
<img src="https://ifh.cc/g/qM16AS.jpg" alt="enter image description here"></p>
<blockquote>
<p><strong>git push오류</strong><br>
로컬저장소의 [master] 브랜치와 연결된 원격저장소의 브랜치가 없어서 발생한 오류이다.</p>
</blockquote>
<blockquote>
<p><strong>GitBash에서</strong></p>
<ul>
<li>긴명령 : (-- ) 대시두개,</li>
<li>짧은 명령 :  (-) 대시 한개</li>
</ul>
</blockquote>
<p><strong>◼ git push 재시도</strong><br>
<img src="https://ifh.cc/g/SMMYmm.jpg" alt="enter image description here"></p>
<blockquote>
<p>-u 옶션을 지정해서 push가 정상적으로 작동<br>
orgin/master브랜치도 생겨났다.<br>
[head]는 항상 현재 작업 중인 브랜치 혹은 커밋을 카리킨다.<br>
더이상 push할 내용이 없다는 뜻 -&gt; "<em>Everything up-to-date</em>’</p>
</blockquote>
<p><strong>◼ git clone 사용해보기</strong><br>
<img src="https://ifh.cc/g/XAT4qS.jpg" alt="enter image description here"></p>
<blockquote>
<p><strong>git clone 실패?</strong><br>
:[새로운 폴더명] 옵션을 지정하지 않으면 복제한 프로젝트 이름과 같은 폴더를 만들게 되는데 이미 같은 폴더명이 있기 때문에 실패한것.</p>
</blockquote>
<h3 id="git-clone">git clone</h3>
<pre><code>$ git clone &lt;저장소주소&gt; [새로운 폴더명]
</code></pre>
<p>:저장소 주소에서 프로젝트를 복제해온다.<br>
:새로 생길 폴더명은 생략 가능하며 폴더명을 생략하면 프로젝트 이름과 같은 이름의 폴더가 새로 생성된다.<br>
:저장소 주소는 꼭 원격일 필요가 없으며 로컬저장소도 git clone명령으로 복제할 수 있다.</p>
<p><strong>◼ git clone으로 로컬저장소 복제하기</strong><br>
<img src="https://ifh.cc/g/TA2a0i.jpg" alt="enter image description here"></p>
<blockquote>
<p>hello-git-cli2 / hello-git-cli내용이 들어가 있다</p>
</blockquote>
<p><strong>◼ 추가 commit and push</strong><br>
<img src="https://ifh.cc/g/uoTYcA.jpg" alt="enter image description here"><br>
<img src="https://ifh.cc/g/nVM4UM.jpg" alt="enter image description here"></p>
<p><strong>◼ git pull</strong><br>
<img src="https://ifh.cc/g/tz5SND.jpg" alt="enter image description here"></p>
<blockquote>
<p>❕ pull = fetch + merge<br>
hello-git-2 의 내용을 원본파일에 pull 하면 hello-git-2의 내용이 전부 담기게 된다.</p>
</blockquote>

