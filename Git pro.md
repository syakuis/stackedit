## 서버 브랜치를 내려받을 때 병합하지 않고 재배치하기.

서버 브랜치를 병합하거나 pull and push 할 경우 불필요한 커밋이 생성되어 좋지 않습니다.

**terminal command**
```
$ git rebase origin/develop
```
‌
**sourceTree**

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lbxlarep6uBI4CiVh7F%2F-Lc5pyrS8fj86aQyJIpX%2F-Lc5x9XYcnvt2s_U26yV%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202019-04-10%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%208.05.52.png?alt=media&token=8c07abf8-f34b-45f1-ba8a-ed642a4cf738)

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lbxlarep6uBI4CiVh7F%2F-Lc5pyrS8fj86aQyJIpX%2F-Lc5x9X_D3MR-WVvon4l%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202019-04-10%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%208.06.08.png?alt=media&token=d49af005-11bd-448e-8e73-3feda04c8eae)

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Lbxlarep6uBI4CiVh7F%2F-Lc5pyrS8fj86aQyJIpX%2F-Lc5x9XbZ69Umxh7eLP2%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202019-04-10%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%208.06.14.png?alt=media&token=d22aad0f-d595-4a42-acd1-5ad33c73aa35)



‌

## 특정 파일만 병합하기

```
$ git checkout -p 브랜치명|커밋id 대상파일
```
‌바로 작성하지 않고 --patch(-p) 옵션을 이용하여 선택할 수 있다.

> [https://junhobaik.github.io/git-specific-files-merge/](https://junhobaik.github.io/git-specific-files-merge/)

‌
## Rebase

```
// 커밋 재배치
git rebase -i 커밋id

// 이전 커밋가 합치기
pick 4c57e8a 2.2.10.RC1
squash b638816 2.2.10.RC1

// 도움말
--abort 중지
--continue 실행
--edit-todo 수정

reword 커밋 수정
squash 이전 커밋 합치기
fixup 이전 커밋과 합치지만 커밋 로그는 제거
```

‌

## 현재부터 특정 커밋까지 압축하기

```
$ git archive -o archive.zip HEAD $(git diff --name-only 5.0.20..5.0.21)
```
‌

## 이전 커밋과 비교

```
$ git diff --cached
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQwMzQ3OTE2MF19
-->