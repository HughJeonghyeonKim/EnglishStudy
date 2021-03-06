<pre>
<h1>1장</h1>
데이터는 텍스트, 영상, 음성, 전자 메일 등 다양한 종류를 가지지만 리눅스는 이 모두를 파일이라는 개념으로 취급
파일을 모아두는 장소가 directory디렉터리(디렉터리 안에 디렉터리가 존재할 수 있다.)
디렉터리는 트리구조를 가진다. 트리 구조가 시작하는 제일 위에 있는 디렉터리가 root directory루트 티렉터리라 한다.
현재 디렉터리: 현재 위치한 디렉터리
홈 디렉터리: 로그인하면  위치하는 개인 전용 디렉터리
현재 디렉터리에 있는 파일과 디렉터리만 사용자가 직접 조작 가능
따라서 현재 디렉터리에 없는 외부파일과 디렉터리는 두가지 방법으로 사용
1. 조작 대사잉 존재하는 디렉터리로 이동
2. 조작 대상을 지정할 때 대상이 존재하는 디렉터리도 지정

절대 경로: 루트 디렉터리에서 시작, 목적지 디렉터리로 향하는 경로
/home /asd 와 ~asd 둘다 홈 디렉터리를 나타낸다
상대경로: 현재 자신의 위치, 즉 현재 디렉터리에서 목적지를 향하는 경로를 나타낸다
현재 디렉터리가 다르면 목적 디렉터리가 같더라도 경로는 달라진다
상대 경로 지정시 .이나 .. 기호를 사용한다
.은 현재 디렉터리, ..은 상위 디렉터리
./은 생략가능

경로 표시 형식
/디렉터리/..../파일		절대경로 표기
./파일			상대경로 표기
파일			./생략한 상대경로 표기

간략화 표현
.			현재 디렉터리
..			상위 디렉터리
~			자신의 홈 디렉터리
~사용자명		특정 사용자 홈 디렉터리

asd 파일 표현		
/home/maltman/asd	절대경로 표기
./asd			상대경로 표기
asd			상대경로 표기에서 ./생략
~/asd			홈 디렉터리에서 시작한 상대 경로 표기
~사용자명/asd		특정 사용자 홈 디렉터리 기준의 상대 경로 표기

사용자, 그룹, 권한
유닉스 계열 OS는 컴퓨터 한 대를 여러 사람이 동시에 로그인하여 사용 가능
따라서 OS사용자를 사용자 ID(User ID)라는 숫자로 관리
사용자 ID와 별개로 사용자명을 문자열로 사용

몇몇 사용자를 묶어 그룹으로 관리하기도 함
사용자는 반드시 하나 이상의 그룹에 속해야 함
사용자가 주로 속하는 그룹은 프라이머리 그룹
*사용자가 새로 작성한 파일이난 디렉터리는 사용자가 속한 프라이머리 그룹 소속이 된다.
그룹 또한 사용자 ID와 마찬가지로 그룹ID라는 번호를 할당

리눅스는 동시에 중복 접근하여 발생하는 오류를 관리하기 위해 권한을 부여한다.
ex)users그룹에 속한 사람만이 읽기가 가능하며 속하지 못하면 읽기 불가능 또한 소유자만 파일을 편집할 수 있다. 그룹에 속하더라도 소유자가 아니면 파일 편집 불가능
어떠한 파일에 쓰기 권한이 부여되면 소유자가 아닌 그룹에 속한 유저도 쓰기가 가능하다.


<h1>2장</h1>
man [명령어 명]		명령어 명의 도움말
ls --help			도움말

mkdir=====
mkdir [name]		디렉터리 작성
mkdir [name] [name] 	복수의 디렉터리 작성
mkdir -p	[name]/[name]	디렉터리 생성과 동시에 서브 디렉터리를 작성
추가적인 옵션-m mode

파일 표시
ls======
ls			현재 디렉터리 안의 파일 표시
ls [name]			name디렉터리 안의 파일 표시
ls -F			현재 디렉터리 안 파일 분류기호와 함께 표시
ls -l			현재 디렉터리 안 파일 분류기호 "없이" "상세정보" 표시
ls -lF			현재 디렉토리 안 파일 분류기호 "있이" "상세정보" 표시
ls -a			현재 디렉토리 안 파일 닷 파일과 함께 표시
추가적인 옵션 -d, -R, -h, -1, --color-auto, -t	

파일 내용 표시
cat=====
cat file1			flie1 파일 내용을 표시
cat file1 file2 file3		file1, file2, file3 파일을 이어서 표시
cat file1 file2 > file3	file1 과 file2 파일을 이어서 출력해 flie3파일로 저장(기존에 입력된 값 사라짐) 
cat > file1		입력한 내용을 flle1로 저장(기존에 입력된 값 사라짐) Ctrl + d 입력 종료
추가적인 옵션 -n -b -A

파일 복사
cp=====
cp file dir			file 파일을 dir디렉터리에 복사
cp file1 file2 file3 dir	file1 file2 file3 파일을 한꺼번에 dir디렉터리에 복사합니다.
cp -r dir1 dir		dir1 디렉터리를 통째로 dir 디렉터리에 복사
cp -i file1 dir		dir에 file1과 같은이름의 파일이 존재한다면 overwrite를 할건지 묻는다? 답은 y || n
추가적인 옵션 -f -d -p -v -a -u

파일 이동
mv=====
mv file dir		file파일을 dir디렉터리로 옮깁니다.
mv file1 file2 dir1 dir	file1, file2 파일과 dir1 디렉터리를 한꺼번에 dir 디렉터리로 옮깁니다

추가적인 옵션 -i -f -v -b -u

파일명 변경
mv=====
mv file1.txt file2.txt		file1이 file2로 이름이 바뀐다.
(.txt를 붙인이유는 .txt를 붙이지 않으면 .txt파일이 아닌 file2로 바뀐다. 그래서 같은 .txt파일로 이름을 바꾼 것.
즉, 기존에 설명한 것과 다르게 확장자명을 써준 이유는 기능을 더 정확히 설명하기 위함)
mv dir dir22		dir이 dir22로 이름이 바뀐다 하위 폴더와 파일의 이름과 내용을 동일
cp=====
cp dir/test.txt ./test22.txt	dir 디렉터리에 있는 test.txt파일을 ./현재 디렉터리에 test22.txt라고 이름을 바꾸어 복사한다.

공통의 추가적인 옵션 -i -f
cp의 추가적인 옵션 -r -p

파일 삭제하기
rm=====
rm file1.txt		file1.txt를 삭제한다(디렉터리는 삭제 불가)
rm file1.txt file2.txt		file1.txt file2.txt 를 한번에 삭제한다.
rm -i file1.txt		삭제 여부를 물어본다
추가적인 옵션 -f

파일 날짜 변경
touch=====
date			현재 시각 표시
touch dir			현재 시각으로 파일의 날짜를 변경
touch -t 202205050323 new	임의의 시간으로 파일의 날짜 변경
touch 없는 파일 명		크기가 0인 빈 파일을 입력한 명대로 파일이 생성된다
추가적인 옵션 -c -rfile

현재 디렉터리 표시, 변경
pwd=====
pwd			현재 디렉터리 표시
cd dir			dir디렉터리로 이동합니다
cd			홈 디렉터리로 이동합니다.

디렉터리 삭제
rmdir=====
rmdir dir1/dir2		dir1의 dir2삭제
rmdir dir1		dir1이 비어있지 않다면 삭제하지 못한다.
rm=====
rm -r			비어있지 않은 디렉터리도 통째로 삭제
rmdir 추가적인 옵션 -p
rm 추가적인 옵션 -r -i -f

프로그램이 존재하는 경로 표시하기
which ls			ls 명령어 프로그램이 존재하는 경로 표시
whereis pwd		pwd명령어와 관련된 파일 경로를 표시합니다
whereis -m rm		rm 먕량아 더음밀 경로만 표시합니다
whereis -B \bin \usr\bin -f crontab		프로그램 검색 경로를 \bin, \usr\bin으로 지정해서 crontab 명령어 프로그램이 존재하는 경로를 펴시합니다.
which 추가적인 옵션 -a
whereis 추가적인 옵션 -b, -s, -M path, -S path, -f

터미널 출력 내용 지우기
clear=====
clear			터미널 출력 내용을 지웁니다.
</pre>
