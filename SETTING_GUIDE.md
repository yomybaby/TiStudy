타이타늄 강좌 참석에 앞서 꼭 필요한 설정들입니다. 다운로드 용량이 큽니다. 사전에 반드시 준비하고 오시기 바랍니다.

# 1. Titanium Studio 및 Titanium SDK 설치

1. Appcelerator 가입 / 로그인하여 해당 OS에 맞는  Titanium Studio 다운로드 후 설치
https://my.appcelerator.com/auth/signup
1. Titanium Studio 다운 및 설치 설치 
	* Mac : http://titanium-studio.s3.amazonaws.com/latest/Titanium_Studio.dmg
	* Win : http://titanium-studio.s3.amazonaws.com/latest/Titanium_Studio.exe
	* Linux32 : http://titanium-studio.s3.amazonaws.com/latest/titanium.linux.gtk.x86.zip
	* Linux64 : http://titanium-studio.s3.amazonaws.com/latest/titanium.linux.gtk.x86_64.zip
2. Titanium 설치 후 첫 실행하면에서 Login 정보 입력
1. 첫 실행시 alloy, node 등을 설치하라는 popup 나오면 지시에 따라 설치

# 2. Platform SDKs
원하는 개발 환경에 따라 Android 및 iOS 개발환경을 설정해야 합니다. 강좌는 Android와 iOS를 다룹니다.
1. Titanium Studio 실행 후 나오는 Dashboard 에서 GetStarted 탭의 하단에 Configure Native SDKs 정보가 나옴.
2. 설명에 따라서 Android SDK를 설치하세요.
3. iOS의 경우는 맥에서만 개발 가능하며 Mac AppStore에서 Xcode 설치만 하면 됩니다.
4. 설치 완료후 Dashboard 새로고침하면 Configure Native SDKs에 해당 Andorid SDK에 초록불이 들어오면 성공 (초록불이 안들어 올경우 해당 메시지에 따라 필요한 sdk를 선택하여 설치합니다.)


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
