# 1. Titanium 설치 및 SDK 설치

1. Appcelerator 가입 / 로그인하여 해당 OS에 맞는  Titanium Studio 다운로드 후 설치
https://my.appcelerator.com/auth/signup
1. Titanium 설치 후 첫 실행하면 Login 정보 입력
1. 첫 실행시 alloy, node 등을 설치하라는 popup 나오면 지시에 따라 설치
1. Dashboard 에서 GetStarted 탭의 하단에 Configure Native SDKs 정보가 나옴
1. Android SDK 선택후 오른쪽에 나타나는 Install Android SDK 클릭
1. android sdk가 저장될 경로 설정 ( 예) C:\User\사용자명\dev\android_sdk , ~/dev/android_sdk )
1. 설치 완료후 Dashboard 새로고침하면 Configure Native SDKs에 해당 Andorid SDK에 초록불이 들어오면 성공 (초록불이 안들어 올경우 해당 메시지에 따라 필요한 sdk를 선택하여 설치합니다.)

# 2. Xcode
맥(OSX) 컴퓨터 일 경우 Mac AppStore에서 Xcode 설치

# 3. Android GenyMotion Emulator
빠른 시뮬레이터를 vm으로 제공하는 서비스입니다. 무료로도 기본적인 사용을 할 수 있습니다.

1. http://www.genymotion.com 가입 후 다운로드
2. Genymotion 실행후 원하는 '+' 아이콘 클릭하여 에뮬레이터 이미지 다운로드
	* 실습에서는 Galaxy Nexus-4.1.1-with Google Apps-API 16 - 720x1280 을 사용합니다.

# 4. 기타 빠른 개발을 도와주는 도구 설치
mac일 경우 아래 명령어 앞에 sudo를 추가해서 실행하세요.

* tishadow 설치 : `npm install -g tishadow`
	* 개발할 때 빠르게 시뮬레이터와 디바이스로 실행시켜주는 툴 
	* http://tishadow.yydigital.com
* gittio cli 설치 : `npm install -g gittio`
	* titanium 모듈과 alloy Widget을 쉽게 isntall/uninstall 시켜주는 도구
	* http://gitt.io
