---
title: "[Git] fatal: not a valid object name: 'main’ 해결 방법"
date: 2024-02-25 +0900
categories: [Git/GitHub, error]
tags: [Git, GitHub, error]
order: 1
---
git으로 branch를 만드려다가 해당 오류가 발생 했습니다.

![Untitled](/assets/img/2024-02-25-Git-fatal-not-a-valid-object-name-해결방법/Untitled.png)

### 원인

아직 commit을 한번도 하지 않은 저장소이기 때문입니다.

### 해결방법

최소 1번이상 commit을 진행하면 됩니다.

```bash
$ vim README.md
```

```bash
:wq
```

```bash
$ git add .
```

```bash
$ git commit -m "initial commit"
```

commit을 하고 난 후 다시 branch를 생성해 보면 아래와 같이 잘 생성 되는 것을 확인할 수 있습니다.

![Untitled](/assets/img/2024-02-25-Git-fatal-not-a-valid-object-name-해결방법/Untitled%201.png)