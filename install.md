설치 방법
=============

## 패키지 파일을 사용하여 설치하기

github의 저장소에서 relrease된 패키지 파일을 다운받아 설치하면 됩니다. relrease 목록은 <https://github.com/Thestars3/arkzip/releases>에서 찾아 볼 수 있습니다.

터미널에서 설치하기 : `sudo dpkg -i <arkzip 패키지 파일의 경로>`

## 직접 컴파일하기

1. 컴파일에 필요한 패키지를 설치.

	`sudo apt-get install libqt4-dev libboost-program-options-dev fakeroot`

2. 이 파일이 위치한 디렉토리로 이동

	`cd arkzip`
	
3. libunhv3 서브 모듈을 다운로드(만약, git 프로그램이 없거나 버전문제로 동작하지 않는다면 수동으로 libunhv3를 다운받아 libunhv3 폴더에 넣는다)

	`git submodule init`
	`git submodule update`

4. 빌드
	
	`qmake`
	`make`

5. deb 패키지 파일을 생성(소스폴더에 dist폴더가 생성되니, 해당 경로는 비워둬야 합니다.)

	`cd ..`
	`./dist.sh`

6. 관리자 권한으로 패키지 파일을 설치

	`sudo dpkg -i *.deb`
