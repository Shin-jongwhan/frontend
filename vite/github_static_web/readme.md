### 250521
# github static web 배포하기
## git repo 생성
### 아래 주소로 하나 생성하였다.
#### https://github.com/Shin-jongwhan/cognimosyne
#### ![image](https://github.com/user-attachments/assets/10801d96-b2f7-432a-bbb4-686788b803a1)
#### <br/>

### github repo settings
#### ![image](https://github.com/user-attachments/assets/3df46c04-f9cc-4cc8-89fb-b52175424859)
### <br/>

### 먼저 테스트 프로젝트를 하나 생성하였다. 아래 내용 참고.
#### https://github.com/Shin-jongwhan/frontend/tree/main/vite/react
### <br/>

### 깃허브로 푸시할 때 기본 구성을 도와주는 패키지 설치
```
npm install --save-dev gh-pages
```

### 그리고 git init, push를 한다.
```
# git init
git config --global user.name "Shin-jongwhan"
git config --global user.email "shinejh0528@gmail.com"
git config --global credential.helper cache
git config --global credential.helper store
git config --global --add safe.directory "C:/Users/shine/Desktop/script/test/vite_project/mcp-test"
git remote add origin https://github.com/Shin-jongwhan/cognimosyne.git

# main branch 생성(git checkout -b main)은 main branch가 없을 경우 한다.
git checkout -b main
git add .
git commit -m "initial commit"
git push -u origin main
```
### <br/>

### deploy
#### 이 명령어는 git push를 하고나면 꼭 해줘야 한다.
```
npm run deploy
```
#### <br/>

### 이제 아래 주소로 홈페이지에 접속해본다.
#### https://shin-jongwhan.github.io/cognimosyne/
