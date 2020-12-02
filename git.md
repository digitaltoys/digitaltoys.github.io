stage (임시) -> HEAD (로컬) -> origin (서버)
add                   commit             push

git clone ssh://ds5042.kim@gpro.lge.com:29418/webosose/test-apps
또는
git remote add origin ssh://ds5042.kim@gpro.lge.com:29418/webosose/test-apps     (로컬에서 처음 업로드할때)

기본
git log
git add *                (stage에 추가)
git status               (stage 확인)
git commit -m "comment" (로컬 HEAD에 적용)
git push origin master    (서버 master에 적용)
git push origin HEAD:refs/for/master
git pull                   (서버 내용 가져오기)

git reset --hard      (모든변경사항 원복)
git checkout -- src/hello.c  (특정파일 원복)
git tab 1.0.0 1b2e1d63ff   (확정본 식별자로 tag달기)
git log                    (확정본 식별자 보기)
git show [commit명]      (특정 commit의 log 확인)
git remote -v          (원격 저장소 확인)
git mv oldName newName (파일 이름변경)

삭제파일 복구(커밋 전)
git ls-files -d (삭제한 파일목록)
git checkout <삭제한 파일명> (삭제한 파일 복구)
git ls-files -d | xargs git checkout -- (삭제 목록에 있는 모든파일복구)
삭제파일 복구(커밋 후) - 삭제된 커밋의 위치를 알아야 한다
git rev-list -n 1 HEAD -- <file_name> (삭제커밋 찾기)
git checkout <커밋>^ -- <파일명>

브랜치
git branch -r            (리모트 브랜치 목록보기)
git branch                (브랜치 목록보기)
git checkout -b branch1 (브랜치생성 & 이동)
git checkout master (브랜치 이동, 소스전환)
git branch -d branch1    (브랜치 삭제)
git push origin branch1 (서버에 브랜치 적용)
git checkout remotes/origin/@498.gld4tv.photovideo.enact-auto

병합
git merge branch1  (브랜치의 내용을 master에 병합)
git diff <org-branch> <tagert-branch> (비교)

검색
git blame ./App.js -L 311,311    (App.js에서 311라인 수정 확인)
