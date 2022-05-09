
## WSL2와 windows Linux에서 Xming GUI를 실행 하는 방법
<br>
<br>

<br>
<br>

1. Xming 홈페이지에서 다운로드
2. Xming 아이콘에서 속성 - 바로가기 - 대상 에서 맨 끝에 (띄어쓰기)-ac를 추가 
3. Windows PowerShell 관리자 권한에서 명령어 실행
4. windows Linux에서 IP주소 획득후 display 환경변수 설정
5. xming GUI 테스트
<br>
<br>

<br>
<br>


---
### 1. Xming 홈페이지에서 다운로드
<br>
<br>

1.1 홈페이지에 들어가서 Releases에서 Xming으로 되어 있는것을 다운로드 한다.


![image](https://user-images.githubusercontent.com/102947384/167357056-e5b85593-9c78-426e-9703-e8c476122e22.png)

<br>
<br>

1.2 이때 _Create a desktop icon for Xming_ 이 것을 체크하여 아이콘을 한게 만든다.
![image](https://user-images.githubusercontent.com/102947384/167357564-26fcdf6d-21f5-4b99-9a0d-80874c816320.png)

---
### 2.  Xming 아이콘에서 속성 - 바로가기 - 대상 에서 맨 끝에 (띄어쓰기)-ac를 추가
<br>
<br>


2.1 Xming에서 외부 IP를 요청하기 위해서 -ac 옵션을 넣어준다.

2.2 아이콘에서 속성을 누른다.

2.3 속성에서 바로가기를 누른다.

2.4 대상에서 끝으로가서 띄어쓰기를 한다음 -ac를 적어준다.

![image](https://user-images.githubusercontent.com/102947384/167358661-95e738f2-643a-470a-9a94-59666deb83b1.png)

---

### 3. Windows PowerShell 관리자 권한에서 명령어 실행

3.1 관리자 권한으로 들어 간다 음

---
### 4. windows Linux에서 IP주소 획득후 display 환경변수 설정

---
### 5. xming GUI 테스트
