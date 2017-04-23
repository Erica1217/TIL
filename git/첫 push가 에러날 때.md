# 첫 push가 에러날 때
첫 push가 에러나서 찾아봤다.

```
error: failed to push some refs to 'https://github.com/Erica1217/TIL'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

github에 올라간 README.md파일이 없어서 나는 오류였다. 그래서 pull로 기존 파일을 가져온 후, push를 하려고 했다. 그랬더니 또 
오류가 났다.

```
fatal: refusing to merge unrelated histories
구글 번역기 : 치명적인 : 관련이없는 기록을 병합하는 것을 거부 함
```
검색해보았더니, git bash에서 이렇게 치면 된단다. 아마 둘이 연관성(?)이 없어서 그런 것 같다. 커밋도 하나도 안되어있는데 파일마저 다르다.

```
git pull origin branchname --allow-unrelated-histories
```

[참고 블로그](http://cpdev.tistory.com/51)<br>
[블로그에 나온 stackoverflow](http://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories)