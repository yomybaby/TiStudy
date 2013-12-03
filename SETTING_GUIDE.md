# Titanium 설치 및 SDK 설치
1. OSX 일 경우 Mac AppStore에서 Xcode 설치
1. Appcelerator 로그인하여 해당 OS에 맞는  Titanium Studio 다운로드 후 설치
https://my.appcelerator.com/auth/signup
1. Titanium 설치 후 첫 실행하면 Login 정보 입력
1. 첫 실행시 alloy, node 등을 설치하라는 popup 나오면 지시에 따라 설치 (**주의** node.js의 경우 최신 버전과 호환되지 않을 수 있음 titanium에서 설치를 권장)
1. Dashboard 에서 GetStarted 탭의 하단에 Configure Native SDKs 정보가 나옴
1. Android SDK 선택후 오른쪽에 나타나는 Install Android SDK 클릭
1. android sdk가 저장될 경로 설정 ( 예) C:\User\사용자명\dev\android_sdk , ~/dev/android_sdk )
1. dash board에 나와있듯이 필수 android tool 관련과 android 2.3의 sdk, google-api 등을 선택 (  4.1.2 의 sdk, google-api, x86 도 선택)
1. 설치 완료후 Dashboard 새로고침하면 Configure Native SDKs에 해당 Andorid SDK에 초록불이 들어오면 성공

> OSX Mevericks인 경우 Titanium Studio 3.2 RC버전을 설치해야함. 초기설치시에는 Release Candidate Installer를 통해 설치 권장. http://preview.appcelerator.com/studio/

# 1. Path 설정
path 설정 없이도 가능하나 매번 사용되는 명령어의 경로를 입력해야하는 불편함 발생

## OSX (path)

1. bash_profile에 sdk의 경로 추가
terminal에 아래와 같은 명령어 실행 (**주의!!!** 경로를 자신의 sdk경로로 바꿔준후 실행, 경로명에 띄어쓰기 있으면 띄었쓰기 앞에 \ 추가)

		echo export ANDROID_SDK_ROOT=/path/to/android/sdk >> ~/.bash_profile
		source ~/.bash_profile

2. android 병령어들의 심볼 만들기
아래 명령어를 실행

		sudo ln -s $ANDROID_SDK_ROOT/tools/android /usr/bin/android
		sudo ln -s $ANDROID_SDK_ROOT/tools/emulator /usr/bin/emulator
		sudo ln -s $ANDROID_SDK_ROOT/platform-tools/adb /usr/bin/adb
3. titanium.py 

		echo alias titanium.py=\"~/Library/Application\\ Support/Titanium/mobilesdk/osx/3.1.3.GA/titanium.py\" >> ~/.bash_profile
4.확인  
terminal에서 아래 명령어를 통해 설치 확인

		titanium.py
        android

## Window (path)

1. 환경 변수 설정
제어판 - 시스템 및 보안 - 고급 시스템 설정 - 고급 (탭) - 환경변수 - 사용자변수에 PATH 편집
맨 뒤에 아래와 같이 sdk 경로를 붙여줌

		;C:\Users\yomybaby\AppData\Roaming\Titanium\mobilesdk\win32\3.1.3.GA

1. Python 설치
python이 없으면 설치 필요 (Titanium Studio에 포함된 Python을 이용해도 되나 편의성을 위해 그냥 설치^^)  
[Python 공식 Download 바로가기](http://www.python.org/download/) (Titanium과 호환성을 위해 2.7.x 버전 32bit 로 설치)

1. cmd에서 titanium.py 실행하여 설정 확인


# 2. Android AVD 설정

1. intel CPU를 사용하는 노트북이면 VT를 지원할경우 HAX를 통해 빠른 x86 에뮬레이터 이용가능  
[Intel® Hardware Accelerated Execution Manager](http://software.intel.com/en-us/articles/intel-hardware-accelerated-execution-manager?page=4)에서 OS에 맞는 것을 설치
1. Studio의 설정의 Android에서 기본 sdk를 Android 4.1.2 [x86]으로 하고 Default Screen을  HVGA로 선택
1. Titanium Studio에서 프로젝트 생성
1. Run Android Emulator (실행되는 상단의 에뮬레이터 이름 기억, 다음 단계에서 폴더 찾을 때 필요)
1. ~/.android/avd/ 밑에 방금 생성된 avd 폴더 안의 config.ini 열기 (예 : /Users/YOUR_USERNAME/.android/avd/titanium_X_HVGA_x86.avd)
1. **sd카드 경로 설정 나온 부분을 제외**하고 다 삭제후 아래 붙여 넣고 저장

		avd.ini.encoding=ISO-8859-1
		hw.mainKeys=no
		hw.lcd.density=160
		hw.cpu.arch=x86
		skin.name=320x528
		abi.type=x86
		image.sysdir.1=system-images/android-16/x86/
		hw.gpu.enabled=yes
		hw.gps=yes
		skin.path=320x528
		hw.keyboard=yes
		vm.heapSize=48
		hw.ramSize=512

1. 다시 Studio에서 Run Android Emulator 실행하면 작고 빠른 에뮬레이터에서 실행된다.



# 3. FastDev를 이용하기 위한 설정
변경한 코드의 빠른 확인을 위해 다음 설정이 필요하다.

## OSX (run_fast)
1. [run_fast.js](https://gist.github.com/yomybaby/3e84a1bb4b26727ee2c0) 파일을 다운 받아 workspace 폴더에 넣는다. (파일을 열어 상단 경로 설정을 자신의 경우 맞게 고침)
1. Titanium Studio의 메뉴에서 Run -external tool - external tool configuration  클릭
1.  program에서 오른쪽 마우스 클릭 - new 선택
1.  아래와 같이 각 항목에 입력
1. Run Fast 입력
	* name : Run Fast
	* Location : `/usr/local/bin/node` (설치 환경에 따라 node의 경로를 입력)
	* Working Directory : `${project_loc}`
	* Arguments : `${workspace_loc}/run_fast.js ${project_loc} ${project_name} ${string_prompt:Platform? (s;tishadow, i;ios, a;android):recent}`
1. 먼저 생성했던 프로젝트의 파일이나 폴더 등이 선택된 상태에서 방금 만든 Run Fast External tool 실행

## Window (run_fast)
cmd 에서 workspace로 이동후 아래 실행

		echo alloy compile -c platform=android ^& titanium.py fastdev kill-app > run_fast.bat

1. Titanium Studio의 메뉴에서 Run -external tool - external tool configuration  클릭
1.  program에서 오른쪽 마우스 클릭 - new 선택
1.  아래와 같이 각 항목에 입력
1. Run Fast 입력
	* name : Run Fast
	* Location : Browser file system 클릭하여 방금 생성된 run_fast.bat 선택
	* Working Directory : ${project_loc}
1. 먼저 생성했던 프로젝트의 파일이나 폴더 등이 선택된 상태에서 방금 만든 Run Fast External tool 실행

## Studio 단축키 설정(run_fast)
1. 스튜디오의 Preference 선택하고
	* window : 메뉴에서 window - preference
	* osx : cmd + ,
1. keys에서 Run Last Launched External Tool의 단축키를 다른것과 겹치지 않는 것으로 지정  
(예:  Cmd + Shift + 9 )
