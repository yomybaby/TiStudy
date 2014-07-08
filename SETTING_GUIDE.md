타이타늄 강좌 참석에 앞서 꼭 필요한 설정들입니다. 다운로드 용량이 큽니다. 사전에 반드시 준비하고 오시기 바랍니다.  
좀더 상세한 설명은 appcelerator 공식 문서를 참고하세요.  
http://docs.appcelerator.com/titanium/latest/#!/guide/Installation_and_Configuration.

#### 주의 : 예전에 설치를 했던 분들은 반드시 업데이트를 하고 오세요 강의 진행은 최신버전을 기준으로 합니다. 경우에 따라 예전버전을 사용하실 경우 실행이 안될 수 있습니다.

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
	* 실습에서는 `Google Galaxy Nexus - 4.3 - API 18 - 720x1280` 을 사용합니다.
3. 설치 후 titanium에서 genymotion을 인식 할 수 있도록 다음 명령어를 터미널에 입력합니다. : `ti config genymotion.enabled true`
4. 설치 확인 : Titanium Studio에서 프로젝트 생성후 Run Menu에서 아래와 같이 Genymotion 에뮬레이터에서 추가한 에뮬레이터가 나오는지 확인
<img src="http://cl.ly/image/2G2U2B2j1n1j/genymotion_capture.png"/>

# 4. 기타 빠른 개발을 도와주는 도구 설치
mac일 경우 아래 명령어 앞에 sudo를 추가해서 실행하세요.

* tishadow 설치 : `npm install -g tishadow`
	* sudo를 이용해서 할경우 `Unable to write config file...`에러가 날 수 있습니다. 이럴 경우 `sudo npm install -g tishadow --unsafe-perm` 명령을 이용해 주세요.
	* 개발할 때 빠르게 시뮬레이터와 디바이스로 실행시켜주는 툴 
	* http://tishadow.yydigital.com
* gittio cli 설치 : `npm install -g gittio`
	* titanium 모듈과 alloy Widget을 쉽게 isntall/uninstall 시켜주는 도구
	* http://gitt.io
* sourceTree : http://www.sourcetreeapp.com
	* 강의중에는 git을 사용합니다.git 명령어에 익숙하지 않으신 분은 sourcetree설치를 권장합니다.
