---
title:  "utterances 댓글기능 추가하기"

categories:
  - Gitblog
tags:
  - gitblog
  - minimal-mistakes
  - utterances
last_modified_at: 2022-01-26 13:00:00 +0900
---

### Utterances로 댓글기능 추가하기

jekyll blog theme(minimal-mistakes)

원래는 Disqus로 댓글 기능을 추가하였으나 무겁고 광고가 붙는다는 단점이 있어서 Utterances를 이용해서 추가해보았다.

### Utterances 장점

1. Github은 다수의 개발자가 가입을 해둔 플랫폼이므로 사용하기 좋다.
2. Utterances를 사용하면 Github 저장소의 Issue로 댓글을 관리할 수 있다.
3. 이슈가 등록되면 slack이나 메일이 오게해서 댓글 알람 기능을 구현할수있다.
4. Markdown 문법을 활용해서 댓글을 작성할수있다.

### 1. 설치

![utterance1](/images/2022-01-26-utterances/utterance1.PNG)

<https://github.com/apps/utterances> 에서 install을 해줍니다.

![utterance3](/images/2022-01-26-utterances/utterance3.PNG)

install버튼을 누르면 저장소를 선택하는 화면이 나온다.
이때 전체 repositories를 할것인지 선택한 repositories로 할것인지 선택한다.

### 설정

![utterance4](/images/2022-01-26-utterances/utterance4.PNG)

설치가 완료가 되면 설정페이지로 이동하는데 저장소를 설정한다. repo: `계정명/저장소이름`을 입력하면 된다.



![utterance5](/images/2022-01-26-utterances/utterance5.PNG)

블로그 포스트와 이슈 매핑 방법에 대한 설정을 해준다.


![utterance6](/images/2022-01-26-utterances/utterance6.PNG)

이슈 라벨과 테마설정부분인데 댓글이슈에는 구분을 위해 comments를 붙이도록 설정했다. 굳이 설정하지 않고 넘어가도 된다.

![utterance7](/images/2022-01-26-utterances/utterance7.PNG)

다 입력하고 나면 맨 하단에 Enable Utterance가 있다. 이부분에서 다른 테마들이랑 minimal-mistakes 테마랑 방식이 조금다르다. 원랜 저 스크립트를 복사해서 post의 layout에 넣어주지만

mininal-mistakes 테마에서는 script부분에서 issue-term, theme을 잘 기억해서 config.yml에 넣어야 한다.

### config.yml 수정

1. repository 등록

   ```markdown
   repository               : "hong1995/hong1995.github.io" # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
   ```

2. comments.provider 이용하기

   repository에서 조금 내려보면 utterances를 설정할수있는 부분이있다. 아까 기억해둔  issue-term, theme를 넣어주면 된다.

   ```markdown
   comments:
     provider               : "utterances"
     utterances:
       theme                : "github-light" # "github-light" (default), "github-dark"
       issue_term           : "pathname" # "pathname" (default)
   ```

### utterances.html수정

**includes/comments-providers/utterances.html**을 찾아가서 파일 내용 중심부에 script 설정을 자신이 선택한 옵션에 맞게 수정한다.

```markdown
var script = document.createElement('script');
    script.setAttribute('src', 'https://utteranc.es/client.js');
    script.setAttribute('repo', 'hong1995/hong1995.github.io');
    script.setAttribute('issue-term', 'pathname');
    script.setAttribute('theme', 'github-light');
    script.setAttribute('label', 'blog-comment');
    script.setAttribute('crossorigin', 'anonymous');
```



### 결과

![utterances8](/images/2022-01-26-utterances/utterances8.PNG)

댓글창은 뜨나 댓글을 작성하면 등록이 되지않았다...
원인을 찾아보니 repository에 이슈를 활성화 시키지 않았었다
utterances가 github 저장소 이슈탭에 댓글을 복제하는 방식으로 동작하는데,
댓글을 복제할 공간이 없어서 등록이 되지 않았던 것이다.

![utterances10](/images/2022-01-26-utterances/utterances10.PNG)

issue를 생성해주었더니

![utterances9](/images/2022-01-26-utterances/utterances9.PNG)

![utterances11](/images/2022-01-26-utterances/utterances11.PNG)

잘 동작하는 것을 확인할 수 있다.
