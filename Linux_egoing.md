# Linux_Egoing
link: https://www.inflearn.com/course/%EC%83%9D%ED%99%9C%EC%BD%94%EB%94%A9-%EB%A6%AC%EB%88%85%EC%8A%A4-%EA%B0%95%EC%A2%8C/dashboard

***

## 환경설정
### OSX terminal
search -> terminal

***

## 리눅스 기초
### file & directory
명령어를 통해서 제어(CLI: Command line interface)

#### 현재 다렉토리에 파일들의 목록을 보기
    ls   
    ls -l   (파일과 디렉토리들을 자세히 보여줌)
    ls -a   (숨겨진 파일들을 포함해서 모든 파일과 디렉토리들을 보여줌)
    ls -al  (모든 파일과 디렉토리들을 자세히 보여줌)(ls -la도 가능)
    ls -S   (파일 사이즈에 따라 정렬해서 보여줌)

```
여기서 앞이 -인 것들은 파일이고 d인 것은 폴더이다.

-rw-r--r--   1 refigo  staff    388  3 20 21:42 a.c
-rwxr-xr-x   1 refigo  staff  49520  3 21 12:14 a.out
drwxr-xr-x   7 refigo  staff    224  3 21 12:46 github-repository
```

#### 현재 위치하고 있는 디렉토리를 알려줌
    pwd
    (print working directory)

#### 현재 디렉토리의 하위에 새로운 디렉토리 만들기
    mkdir 새로_생성할_디렉토리명
    
    ex)   
    mkdir hello_linux

    mkdir -p 원하는_디렉토리_경로들
    ex)
    mkrdir -p dir1/dir2/dir3/dir4

#### 비어있는 파일 생성
    touch 파일_이름

    ex)
    touch empty_file.txt

#### 디렉토리를 이동하기(change directory)
    cd 이동할_디렉토리의_경로명

    ex)
    cd hello_linux/
    (쓰다가 중간에 tab키를 누르면 자동완성이 된다.)

#### 부모 디렉토리로 돌아가기
    cd ..
    (현재 머무는 디렉토리의 부모 디렉토리는 ..을 쓰자고 약속함)

#### 최상위 디렉토리로 부터 가고자 하는 파일로 이동하기(절대경로)
    cd /home/ubuntu
    (처음 /는 root directory다.)

#### 창 깨끗하게 만들기
    clear

#### 파일이나 디렉토리 삭제하기
    rm 파일명
    ex)
    rm empty_file.txt

    rm -r 디렉토리명
    (디렉토리를 삭제하는 것은 위험할 수 있으니 옵션을 추가해야한다.)
    (-r은 --recursively)
    ex)
    rm -r hello_linux
    rm -r hello_linux/

### help & man
명령어들에 대해서 자세한 설명을 보기

#### 명령의 사용설명서, 도움말 보기
    명령어 --help
    (mac os에서는 안 됨, 대신 man을 이용)
    ex)
    rm --help

    man 명령어
    ex)
    man ls
    (man은 전용페이지로 이동하여 상세한 설명을 보여준다)

##### man에서 여러 단축키들을 이용해 조작한다
    - 검색
    /검색명
    ex)
    /sort
    (n을 눌러서 검색한 다음 단어로 이동)

    - 나가기
    q

대문자와 소문자를 잘 구분해라

### 필요한 명령을 검색으로 찾는 법
예제, 문법 먼저 보고 더 이해하고 싶으면 목표 범위를 좁히고 읽자

#### make directory in linux !g
    mkdir dirname

#### file copy in linux !g
    cp 파일위치_및_파일이름 목적지

#### move file in linux !g
    mv 원본파일 이동될위치
    // 이름을 바꿀 때도 mv를 쓴다
    ex)
    mv rename.txt rename2.txt

지식을 찾아내는 방법이 중요하다.   
시간이 지날수록 경험이 축적되어서 많은 지식을 자연스럽게 알게 되는 것이 중요하다.

### sudo
sudo(super user do)

유닉스 계열의 중요한 특성 중 하나는 다중 사용자 시스템

사용자마다 권한을 부여

super user or root user

치명적 실수 방지
    ex)   
    rm -rf  (root directory에 있는 파일을 강제삭제)
    (이런 명령어를 실수로 사용하면 위험해지기 때문)

경우에 따라 super 유저의 권한이 필요할 때 sudo 사용

    ex)
    apt-get install git
    (git설치_sudo필요)
    sudo apt-get install git

### nano 에디터 사용하기
초급 nano   
중/고급 Vi

    nano
를 입력해서 사용

### Package manager(Window)
마치 앱스토어 역할

리눅스에서 대표적인 패키지 매니저   
apt   
yum   

apt 위주로 설명   

패키지 매니저를 통해서 설치할 수 있는 소프트웨어의 목록을 최신 상태로 갱신하기   
    apt-get update;   
    sudo apt-get update;   

검색(htop)   
    sudo apt-cache search htop   
    (cache는 저장된이라는 의미와 비슷한데 저장한 목록에서 찾는듯)   

현재 컴퓨터에서 실행되고 있는 프로그램의 목록 보여줌   
    top   

빠져나가기
    q

htop 프로그램 다운
    sudo apt-get install htop
htop은 top보다 좀 더 graphical 하다

업그레이드
    sudo apt-get upgrade htop

모든 프로그램 확인
    sudo htop

삭제
    sudo apt-get remove htop

### 맥 사용자를 위한 homebrew(package manager in mac)
검색, 설치, 삭제

terminal에 코드 paste

    brew help

htop 프로그램으로 실습

    brew search htop

    brew install htop

    sudo htop

설치한 프로그램 list
    brew list   

htop 삭제
    brew uninstall htop

vim을 upgrade
    brew upgrade vim   

설치한 모든 프로그램 전체적으로 upgrade
    brew upgrade   

다운 가능 목록 최신화
    brew update   

### file download : wget
다운 받을 때 필요한 프로그램   
    wget

URL을 통해서 파일 다운 가능

wget 주소   
URL에 있는 파일 다운

    wget --help

다운 받고 다운 받는 파일의 이름 바로 지정 가능
    wget -O paris.jpeg 주소   


### Source download: git
버전관리 시스템 제품 중 하나

github   
react 오픈소스를 자신의 linux 컴퓨터로 다운로드 받는 방법   
1) 그냥 다운
2) git이라는 버전 관리 프로그램을 통해서 다운   
우리는 2)로 해보자   

clone with HTTPS   
이용(소스코드의 주소)   

[in terminal]
    sudo apt-get install git

오픈소스 프로그램 복제   
    git clone https://github.com/facebook/react.git react_src
react_src라는 directory에 주소가 가리키는 오픈소스 프로젝트가 다운로드 됨

***

## IO Redirection
### IO Redirection - output

redirection 방향을 바꿈   

ls -l 목록을 파일에 저장하고 싶다면
nano ls_result.txt이렇게 해서 붙여넣기 하고 뭐 이런걸 해야하는데 보다 더 쉬운 방법이 있다.
    ls -l > result.txt
이면 출력될 결과가 result.txt라는 파일 안에 저장된다.

    cat result.txt
를 쓰면 같은 내용이 저장된걸 console에서 볼 수 있다.

***
출력되는 방향을 다른 곳으로 돌려서 파일에 저장시킴   
redirection

last time... on the website. Lecture 6 shell scripting.   
라는 ppt에서 볼 수 있음(shell script 공부할 때 좋음)

중간에 원으로 표시된 Unix process(명령어)   
명령어로 예를 들면   
    ls
    apt-get
    ps
    mkdir
같은 것들이 중간에 위치한 process에 해당된다.

이 프로세스는 크게 입력과 출력을 가지고 있는데 가장 기본적인 입력은 Command-line Arguments라고 하는 것이다.   
    ex)
    ls -al
에서 -al이 ls라고 하는 프로그램에 입력으로 들어오는 입력 값 중 하나이다.⭐   
이렇게 실행될 때 전달되는 입력값을 command-line arguments라고 한다.   

정보를 출력하는 것은 standard out이라고 하는 것이다.(모니터에 출력)   
그 모니터에 출력되는 것을 바꿔서(redirection)시켜서 다른 곳으로 출력되게 할 수 있다.   
    ex)
    file
    ls -l > result.txt(파일이름)
화면에 출력되는 것 대신에 redirection으로 result.txt라는 파일에 출력된다.

이제 유닉스, 리눅스 운영체제에서 동작하는 프로세스들의 처리결과를 어떤 특정한 텍스트로 저장할 수 있게 된다.
(본질적인 표현으로는 "방향을 바꿀 수 있다")   
(쉽게는 "파일에 저장할 수 있다.)   

### standard error

유닉스의 프로그램인 프로세스가 출력하는 결과는 크게 두 가지로 구분한다.   
* standard output
* standard error(오류가 있을 때, 오류는 중요한 정보이므로 별도의 출력으로 처리)
이렇게 하기로 했다.

standard error   
    ex)
    rm rename2.txt
하고 삭제된 상태에서 다시 같은 명령을 실행
    rm rename2.txt
하면 에러 메세지가 뜬다.   

    rm rename2.txt > result.txt
를 쳐도 에러 메세지가 뜬다.(output이 redirection 되기를 기대했는데 redirection 안 됨)

\>를 쓰는 것은 standard output을 redirection 하는 것이다.   
(standard error를 redirection 하지 않음)

사실 >앞에 1이 생략되어있다.   
    1>
(>는 redirection을 의미하는데 앞에 1이 붙어있으면 standard output 표준출력을 의미한다.)

error message를 error.log에 저장하고 싶다면
    rm rename2.txt 2> error.log
(standard error라고 하는 정보에 대한 출력을 redirection 함)

    cat error.log
하면 읽을 수 있음

    rm rename2.txt 1> result.txt 2> error.log

실행한 결과는 result.txt에  
실행 중에 발생한 에러는 error.log   
에 보관

### IO Redirection - input
코드로 짠 프로그램이 실행되고 있는 상태를 프로세스라고 한다.   
(하나의 프로그램은 여러 개의 프로세스를 가질 수도 있다.)   

1가지의 입력이 있다.   
standard input   

즉, 하나의 input과 2개의 output이 존재   

    cat hello.txt

cat이라고 하는 프로그램은 두 번째 인자로 파일명이 들어오면   
그 파일 내용을 화면에 출력해준다.   

cat이라는 명령을 그냥 실행시키면   
프로그램이 대기상태에 있는다.   
그 상태에서 어떤 문자를 입력하면   
그러면 cat이라는 프로그램이 입력한 문자를 출력해준다.   
빠져나가고 싶다면 ctrl + d   

즉, cat이라는 프로그램은 사용자가 키보드를 통해서 입력하는 정보를 받는다.   
(standard input)   

redirection 시켜서 파일 안에 있는 내용을 cat의 입력값으로 줄 수 있다.
    cat < hello.txt ⭐

cat hello.txt는 command-line argument를 통해 입력 받음(인자)   
cat < hello.txt는 standard input으로 입력 받음(표준 입력)   

어렵지만 실용적이지 않기 때문에 넘어가도 된다.   
왜냐면 대부분 cat hello.txt 이런식으로 쓴다.   
하지만 standard output은 쓸 일이 많기 때문에 이해하는게 좋다.   

***

긴 텍스트에서 앞 쪽에 일부의 텍스트만 화면에 출력하기
    head linux.txt
하면 기본 10줄만 출력한다.

    head -n1 linux.txt
하면 한 줄만 출력한다.   
(head라는 프로세스에 -n1 linux.txt라는 command-line argument(명령어 인자)를 준 것이다.

만약 standard input을 주고 싶다면
    head -n1 < linux.txt
에서 -n1이 command-line argument이고 <는 standard input을 준거다.   
결과는 위와 같다.

출력된 결과를 다시 txt에 저장하고 싶다면
    head -n1 < linux.txt > one.txt
(표준 입,출력 모두 한 것임 and redirection)

one.txt에 어떤 결과가 있는지 확인하고 싶다면
    cat one.txt

***
input과 output이 흘러나가는 모양을   
IO stream 이라고도 한다.

### IO Redirecton - append
(악세서리 같은 기능들)

    ls -al > result.txt
    ls -al > result.txt
이렇게 연속 두번하면 어떻게 될까?   
-> 한 번 한 것과 똑같다.(실행될 때 마다 결과가 내용을 덮어쓰기 한다.)

이제 하려는 것은   
실행될 때 마다 result.txt라는 파일 내용의 뒤에 추가가 되게 하려고 하는 것이다.(append)
    ls -al >> result.txt
하면 결과가 마지막에 이어져서 추가된다.

즉, >>이면 redirection을 하는데 그 redirection한 결과를 추가한다, 뒤에다가 덧댄다.   
라는 뜻이다.

(명령을 쓰다가 취소할 때는 ctrl + c)

<<를 쓰면 여러개의 입력을 하나로 합친다.   
    ex)
    mail이라는 프로그램 사용(따로 설치해야함)

    mail egoing@gmail.com <<eot
    (입력을 받아서 메일로 보냄)
    hi
    my
    name
    is
    egoing
    eot
    (이렇게 여러줄을 입력하고 마지막에 eot라고 쓰면 입력한 여러개의 정보들이 
    mail이라는 프로세스에 input으로 redirection 되게 된다.)

    mail egoing@gmail.com <<hahahoho
    hello
    It's
    me
    hahahoho
    이렇게 써도 된다.

즉, << 꺽쇠 2개 뒤에 나오는 문자의 의미는 "다음에 이 문자가 등장하면 거기서 입력이 끝나는 것이다."라는 것을 의미하는 특수한 기호다.
(근데 거의 안 씀)

***
출력한 결과를 화면에도 출력하고 싶지 않고 다른 곳에 redirection도 하고 싶지 않다면
    ls -al > /dev/null
이 /dev/null은 유닉스 계열에서는 휴지통 같은 것이다.   
출력값이 /dev/null로 redirection 되면 그냥 사라진다(마치 낭떠러지)

## Shell and shell script
### Shell 1 - intro
Shell vs Kernel

kernel shell !g

[ application [ shell [ kernel [ hard ware ] ] ] ]   

우리가 입력한 명령이 shell을 대상으로 한다.   
shell에게 명령을 입력   

shell은 명령을 해석해서 kernel이 이해 할 수 있는 방식으로 전달   

kernel은 hardware를 제어해서 어떠한 처리를 수행할 수 있게함   

hardware가 처리결과를 kernel에게 알려주고 kernel이 shell에게 알려주면서 우리가 실행된 결과를 볼 수 있다.   

shell이라는 것은 사용자가 입력한 명령을 해석하는 프로그램이다.⭐   

kernel과 shell을 분리하면 여러가지의 shell이 생길 수 있다.   
사용자가 편하게 느껴지는 shell 프로그램을 이용할 수 있다.   

여러가지 shell을 써보면서 shell이 kernel과 구분되는 것을 확인해보자   
shell이 무엇인지 드러내 보자   

### shell 2 - bash vs zsh
linux에 입력
    echo "hello"
    hello(문자를 화면에 출력)

    echo $0
    -bash
    (현재 shell 중에서 shell이라는 카테고리에 속하는 구체적인 제품 중에 하나인 bash라고 하는 프로그램을 쓰고 있는 것임)

zsh(zShell)이라는 것을 써보자⭐
    zsh
그냥 치면 찾을 수 없다고 나옴(설치 안 돼 있음)


설치
    sudo apt-get install zsh

    echo $0
    zsh
    (zsh 사용 중)

bash vs zshell   
부모가 같기 때문에 상당히 유사한 특성 가짐   
zshell의 경우 bash가 갖고 있지 않은 좀 더 추가적인 기능들을 가지고 있음   
기본적으로 bash가 설치되있음(macbook M1은 기본적으로 zsh)   

    cd + tab
    pwd
    ls

명령어의 편의성이 shell 마다 다르다

built-in commands(cd라든지 ls라든지 이런거)

원하는 shell을 선택해서 자신에게 최적화된 환경을 만들 수 있다.

### Shell script 1 : intro
script 대본, 각본   
(배우들이 어떤 흐름으로 연기해야하는지에 대한 흐름이 적혀있음)   

명령이 하나일 수 있지만 아주 많은 경우에는 여러 개의 명령을 순차적으로 실행하는 걸 통해서 어떤 하나의 업무가 이루어지는 경우가 많다.

순차적으로 실행되어야하는 명령의 순서(명령의 각본)을 어딘가 적어놓고 나중에 재사용할 수 있다면 좋다.   
(하루에도 수십번 씩 실행되는 명령어들의 세트나 상당히 복잡한 코드를 가진 명령 등)   
그런 것들은 매번 타이핑하기 보단 어딘가에 저장해놨다가 불러와서 실행시키면 편하다.   

#### shell에서 실행되는 명령들 어딘가 저장하는 방법과 그걸 가져와서 실행하는 방법
자동화된 작업 처리 가능   
많은 명령들이 shell script처럼 동작한다.

    mkdir script
    cd script
    (log 파일들을 bak이란 폴더에 백업하고 싶다)
    명령어 하나하나 실행한다면
    touch a.log b.log c.log
    ls -l
    mkdir bak
    cp *.log bak
    (공통적인 부분을 쓰고 다른 것은 *로 쓴다 > *이 확장자가 log인 모든 파일을 가리키는 기호(와일드 카드))
    ls -l bak

내용이 바껴서 다시 저장하고 싶다면   
back 폴더가 없다면 만들고 있다면 바로 copy
    cp *.log bak

### Shell script 2 : example
shell script를 만들어 보자

    echo $0
    ls /bin
(root안에 있는 bin 폴더에 -bash같은 프로그램이 있다.)
(bin에는 기본적인 프로그램들이 위치해 있다.(유닉스 계열))

/scirpt에서 
nano backup (backup이라는 프로그램 생성)   
#!/bin/bash   
(실행시켰을 때 운영체제는 #! 이렇게 생긴 기호를 본다 그리고 다음 /bin/bash를 보고 이 밑에 작성되는 코드들이 bin 밑에 있는 bash라는 프로그램을 통해서 해석되어야 한다는 사실을 알게된다.)   
(명령어 해석기 파일을 적어주는 것이 약속)   

이제 bash라는 프로그램이 갖고있는 문법을 사용할거다   
(구현하려는 것 :    
현재 디렉터리에 bak라는 디렉터리가 없다면 만들고 있다면 만들지 않는다.   
현재 디렉터리에 있는 모든 파일 중에 .log로 끝나는 파일들을 bak라는 디렉터리로 복사한다.   
    if [ -d bak ]; -> 현재 디렉터리에 bak이라는 디렉터리가 존재하는가?   

    if ! [ -d bak ]; then -> 현재 디렉터리에 bak이라는 디렉터리가 존재하지 않는다면 
        mkdir bak
    fi -> 조건문이 끝났다는 걸 알려줌(조건문 종료)
    cp *.log bak

#### 전체 코드
    #!/bin/bash
    if ! [ -d bak ]; then
        mkdir bak
    fi
    cp *.log bak

backup이라는 파일 실행시키기
    ./backup
(권한 필요)   
(그 파일이 실행 가능한 프로그램이다라는 것을 리눅스에게 알려줘야함)
    chmod +x backup
    ls -l
그러면 backup이 초록색으로 되고 x가 추가됨   
x는 excutable(실행 가능한)   
(+x를 추가해서 실행가능한 모드를 추가해서 change 시킴 chmod)   

    rm -rf bak
    ls -l
    ./backup
    ls -l
    ls -l bak
하면 bak이 삭제 됐다가 다시 생기는 것을 볼 수 있다.

    rm bak/c.log
    ./backup	(현재 디렉터리에 있는 backup)
    ls -l bak

nano backup   
셸 스크립트 확인   
ctrl + x 쓰면 빠져나옴   

# 디렉토리 구조와 파일 찾는 법
## Directory structure
디렉토리는 어떤 데이터나 실행할 수 있는 프로그램을 정리하는 수단   

유닉스 계열에서는 데이터와 실행할 프로그램의 성격에 따라서 정해져 있는 디렉토리에 위치한다.

linux directory structure !g   
Linux Directory Structure (File System Structure) Explained with Examples   

### / - Root
최상위 디레토리(root)
    /

### /bin - User Binaries
bin은 binary를 줄인말   
실행가능한 프로그램을 컴퓨터에서는 바이너리라고도 부른다.⭐   
사용자들이 사용하는 명령들이 위치한다.   

### /sbin - System Binaries
시스템 프로그램   
reboot   
shutdown 등등   

즉 일반 사용자들이 쓰는 것들은 bin에 있고   
관리자 root 사용자가 쓰는 프로그램들은 sbin에 있다고 생각   

### /etc - Configuration Files
설정   
프로그램이 동작하는 방법을 바꿈   
리눅스(유닉스 계열)에서 동작하는 대부분의 프로그램의 설정은 파일을 바꾸는 것   

wget 등이 있다(파일 다운)   
sudo nano wgetrc   

### /dev - Device Files

### /proc - Process Information

### /var - Variable Files
내용이나 용량이 바뀔 수 있는 파일   
var 안에 있는 파일들은 대부분 내용이 바뀔 수 있는 특성을 가지고 있다   

/var/log에 있는 파일 들은 어떤 프로그램이 동작하는 과정에서 에러가 발생하면 특정 파일의 이름에 저장됨(가변적)   
즉, 사용자의 행동에 따라 내용이 변한다.   

### /tmp - Temporary Files
임시 파일   

### /home - Home Directories
사용자들의 디렉토리   
만약 egoing이라는 사용자가 있다면 home 안에 egoing이 있다.   
egoing이라는 디렉터리에는 egoing이 사용하는 파일들이 저장되는 디렉토리    

home directory로 빨리 가는 방법   
    cd ~
(사용자의 홈디렉터리로 한 번에 워프 만약 egoing이라면 egoing 파일로 한 번에⭐)   

    cd ~/dir
이런식으로 사용 가능

### /boot - Boot Loader Files
운영체제의 아주 깊은 곳과 관련   

### /lib - System Libraries
/bin과 /sbin에 있는 프로그램들이 공통으로 사용하는 라이브러리들이 있는 곳

### /opt - Optional add on Application
리눅스에서 프로그램을 다운받아 설치하면 디렉토리 자동 지정 될 때도 있는데 경우에 따라서 특정 디렉터리를 지정해야하는 경우도 있다.   
그럴 때는 /opt밑에 저장하는 것도 좋은 방법이다.

### /mmt - Mount Directory

### /media - Removable Media Devices

### /srv - Service Data

### /usr - User Programs
    /usr/bin
    /usr/sbin
    /usr/lib
    /usr/local
들이 있다.

우리가 설치하는 프로그램들은 usr 밑에 설치가 되고 기본적으로 유닉스 계열에 설치가 되어서 번들 형식으로 사용되는 프로그램들은 /bin이나 /sbin 같은 곳에 저장된다.(root)   
역사적으로는 disk와 관련이 있다. disk의 용량이 매우 작았기 때문에 분리가 되었다.   
역사적인 이유에서 차근차근 분리되면서 여러 디렉토리들이 생기게 되었다.   

## File find 1 : locate, find
원하는 파일이 있을 때 그 파일을 찾는 방법   

크게 파일은 두가지 용도로 사용됨   
1) 데이터를 보관하기 위한 용도   
2) 해야 할 일에 대한 어떤 명령을 보관하고 있는 실행 파일   

### locate

확장자가 .log인 모든 파일을 찾고 싶을 때
    locate *.log
    man locate

locate란 명령은 directory를 뒤지지 않는다.   
데이터베이스를 뒤진다.(정보가 저장돼 있는 공간)   
(컴퓨터에 저장되어 있는 파일들에 대한 정보를 담고 있는 데이터 베이스)   
그래서 훨씬 더 빠르게 파일을 가져올 수 있다.   
locate가 사용하는 데이터베이스를 mlocate라고 부른다.   

    sudo updatedb
를 치면   
mlocate라는 데이터베이스에 현재 이 컴퓨터에 있는 파일들에 대한 여러가지 정보들이 저장된다.   
이 작업은 많은 리눅스 시스템에서 하루에 한 번씩 정기적으로 처리하게 되어있다.   
그러면 미리 파일들의 위치같은 것들을 정리해놨기 때문에 locate를 통해서 파일을 검색하면 훨씬 더 빠르게 파일을 가지고 올 수 있다.

### find
find는 실제로 디렉토리를 뒤진다.   

locate보다 성능상으로는 안 좋을 수 있다.   
하지만 직접 파일을 뒤지므로 현재 상태를 가져올 수 있다.   
굉장히 다양한 사용법들이 있다.   
그러므로 파일을 찾는 것에 있어서 마스터링 툴은 find이다.   

    man find
    find --help
    find --help | head

루트에서 부터 찾기
    find /

현재 디렉토리부터 하위 디렉토리로 찾기
    find .

컴퓨터에 있는 모든 디렉토리를 뒤져서 .log라고 하는 파일을 찾음
    find / -name *.log

permission denied가 생기는 경우에는
    sudo find / -name *.log

홈 디렉에서 부터 찾기
    find ~ -name *.log

확장자 지정
    find . -type f
    (파일이라는 뜻)

    find . -type f -name "tecmint.txt" -exec rm -f {} \;
    (묻지말고 삭제하라(rm -f)는 명령(-exec)을 실행시킴 
    ({}에는 명령을 통해서 검색한 파일의 이름이 위치)

## File find 2 : whereis, $PATH
whereis

    whereis ls
하면 ls의 위치와 man ls할 때 나오는 매뉴얼의 위치를 알려줌

    whereis rm

    man whereis
    -> binary, source and manual files 을 찾고
    $PATH and $MANPATH 라는 것을 뒤진다.

그 중 중요하게 생각할 것은 $PATH라는 디렉토리⭐️

ls는 
    /bin/ls
라고 쳐도 실행된다.   
그럼에도 ls라는 명령어를 어디에서나 입력해도 실행될 수 있는 이유는 무엇일까?   
그 비밀이 $PATH라고 하는 변수에 있다.   

    echo $PATH
하면 $PATH에 있는 데이터들이 echo를 통해서 화면에 출력된다.   
정보들은 :을 통해서 구분된다. 구분된 정보들은 경로를 나타낸다.   
$PATH라고 하는 변수를 우리가 만든 적이 없다. 즉, 리눅스에서 $PATH를 기본적으로 내장한다.   

$PATH에 담겨있는 정보들은 어떤 용도로 사용되냐면   
ls라고 입력해서 전달하면 운영체제가 $PATH라고 하는 변수에 담겨있는 디렉토리들을 검색한다.   
그 디렉토리에 ls라고 하는 실행파일이 존재하는지를 차례대로 뒤진다.   
그리고 ls라는 명령어가 발견되면 그 명령어를 실행한다.(/bin 안에서 ls를 발견하고 실행)   

$PATH 값은 변경이 가능하다.   

이런 변수를 환경변수라고 부른다.   