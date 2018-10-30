# 안드로이드 프로그래밍 과제
# 1. git명령어 정리
>>참고:[https://medium.com/@joongwon/git-git-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC-c25b421ecdbd]

## 1. 설정과 초기화
### 1-1. 전역 사용자명/이메일 구성하기
+ git config - -global user.name “Your name”

+ git config - -global user.email “Your email address”

### 1-2. 저장소별 사용자명/이메일 구성하기 (해당 저장소 디렉토리로 이동후)
+ git config user.name “Your name”

+ git config user.email “Your email address”
>>참고로 user 설정이 되어 있지 않으면 Github에 있는 repository에 변경사항을 푸시 한다고 해도 commit count 집계도 안되고 해당 커밋의 작성자 프로필 아이콘도 ? 로 표시되기 때문에 웬만하면 name과 email 주소를 설정하길 추천한다.

### 1-3. 전역 설정 정보 조회
+ git config - -global - -list

### 1-4. 저장소별 설정 정보 조회
+ git config - -list

### 1-5. Git의 출력결과 색상 활성화하기
+ git config - -global color.ui “auto”

### 1-6.새로운 저장소 초기화하기
+ mkdir /path/newDir

+ cd /path/newDir

+ git init

### 1-7. 저장소 복제하기
+ git clone <저장소 url>

### 1-8. 새로운 원격 저장소 추가하기
+ git remote add <원격 저장소> <저장소 url>

## 2. 기본적인 사용법
>>아래 명령어에서 ( )는 선택적인 매개변수를 의미한다.

### 2-1. 새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기
+ git add <파일>

+ git commit -m “<메시지>”

### 2-2. 파일의 일부를 스테이징하기
+ git add -p (<파일> (<파일> (기타 파일들…)))

### 2-3. add 명령에서 Git 대화 모드를 사용하여 파일 추가하기
+ git add -i

### 2-4. 수정되고 추적되는 파일의 변경 사항 스테이징하기
+ git add -u (<경로> (<경로>))

### 2-5. 수정되고 추적되는 모든 파일의 변경 사항 커밋하기
+ git commit -m “<메시지>” -a

### 2-6. 작업 트리의 변경 사항 돌려놓기
+ git checkout HEAD <파일> (<파일>)

### 2-7. 커밋되지 않고 스테이징된 변경 사항 재설정하기
+ git reset HEAD <파일> (<파일>)

### 2-8. 마지막 커밋 고치기
+ git commit -m “<메시지>” - -amend

### 2-9. 이전 커밋을 수정하고 커밋 메시지를 재사용하기
+ git commit -C HEAD - -amend

## 3. 브랜치
### 3-1.지역 브랜치 목록 보기
+ git branch

### 3-2.원격 브랜치 목록 보기
+ git branch -r

### 3-3. 지역과 원격을 포함한 모든 브랜치 목록 보기
+git branch -a

### 3-4. 현재 브랜치에서 새로운 브랜치 생성하기
+ git branch <새로운 브랜치>

### 3-5. 다른 브랜치 체크아웃하기
+ git checkout <브랜치>

### 3-6. 현재 브랜치에서 새로운 브랜치 생성하고 체크아웃하기
+ git checkout -b <새로운 브랜치>

### 3-7. 다른 시작 지점에서 브랜치 생성하기
+ git branch <새로운 브랜치> <브랜치를 생성할 위치>

### 3-8. 기존의 브랜치를 새로운 브랜치로 덮어쓰기
+ git branch -f <기존 브랜치> (<브랜치를 생성할 위치>)

### 3-9. 브랜치를 옮기거나 브랜치명 변경하기
><새로운 브랜치>가 존재하지 않을 경우
+ git checkout -m <기존 브랜치> <새로운 브랜치>

>무조건 덮어쓰기
+ git checkout -M <기존 브랜치> <새로운 브랜치>

### 3-10. 다른 브랜치를 현재 브랜치로 합치기
+git merge <브랜치>

### 3-11. 커밋하지 않고 합치기
+ git merge - -no-commit <브랜치>

### 3-12. 선택하여 합치기
+ git cherry-pick <커밋명>

### 3-13. 커밋하지 않고 선택하여 합치기
+ git cherry-pick -n <커밋명>

### 3-14. 브랜치의 이력을 다른 브랜치에 합치기
+git merge - -squash <브랜치>

### 3-15. 브랜치 삭제하기
>삭제할 브랜치가 현재 브랜치에 합쳐졌을 경우에만
+ git branch -d <삭제할 브랜치>

>삭제할 브랜치가 현재 브랜치에 합쳐지지 않았어도
+ git branch -D <삭제할 브랜치>
