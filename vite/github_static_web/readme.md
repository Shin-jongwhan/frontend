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
### <br/>

## custom domain 설정
### 먼저 도메인 호스팅 사이트에 접속해서 A record와 CNAME을 추가해줘야 한다.
- A : @, 185.199.108.153
- A : @, 185.199.109.153
- A : @, 185.199.110.153
- A : @, 185.199.111.153
- CNAME : www, shin-jongwhan.github.io
#### ![image](https://github.com/user-attachments/assets/95e61189-08c4-481c-b4fd-1538d3924755)
### <br/><br/>

### custom domain 설정
### CNAME이라는 파일을 하나 만든다.
#### ![image](https://github.com/user-attachments/assets/fcd38fef-eb8f-4021-8941-4a786a82af21)
### github - pages 설정에서 custom domain을 입력하고 기다려야 한다.
#### ![image](https://github.com/user-attachments/assets/1170da06-1fa5-4c51-a859-cfa18f1d0287)
### <br/>

### 다 되면 let's encrypt를 이용해 github에서 자동으로 SSL 설정을 해준다. 인증서 발급에 30분 정도 걸리며, 다 되면 HTTPS 버튼이 활성화된다.
#### ![image](https://github.com/user-attachments/assets/c327aa57-deb3-4c1d-bbf9-df52d39495b7)
### <br/><br/>

## 주의 사항
### windows일 경우 github 말고 직접 웹 앱을 개발하려고 했을 때 hosts 파일을 수정해야 하는데, 이걸 다시 꺼놔야 한다. 
### 그래서 C:\Windows\System32\drivers\etc\hosts 파일에서 주석처리한다.
```
[IPv4 address] cognimosyne.com www.cognimosyne.com
```
### <br/>

### 그 다음 브라우저에서 접속하려고 하면 접속이 여전히 안 될 수도 있는데, 브라우저 캐시를 비워야 한다.
