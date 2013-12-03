# 12월 4일 Ti 강좌

### 0. Ice braking 및 강좌 소개
* 강사 소개
* 수강생 소개
* 강좌 소개
* Titanium의 작동 원리 설명
	* 진행 방식 : 환경설정 여부를 조사하여 환경설정과 적절히 섞어가면서 진행
	* '당신이 알고 있는 타이타늄' 자료 활용


### 1. Titanium 환경설정 
* 기본 타이타늄 설정 - Dashboard 이용
* 설정 확인 및 맛보기 실행
	* 프로젝트 생성
    * tiapp.xml
    * 실행 방법 (ios, android, 실행 옵션 변경하기)
    * CLI로 실행하기
* [강좌를 위한 환경 설정 문서](https://github.com/yomybaby/TiStudy/blob/master/SETTING_GUIDE.md) 참조




### 2. Document 보는 법
* API : http://docs.appcelerator.com/titanium/3.0/#!/api
    * 컴포넌트 명
    * 상속 정보
    * Properties, Methods, Events
    * 지원 플랫폼 정보
    * Property 상세 : 샘플코드, 속성 이름/타입, 지원 플랫폼
* Guide 문서 : http://docs.appcelerator.com/titanium/3.0/#!/guide

## 3. Javascript 기본
[JS Bin](http://jsbin.com)에서 실습하면 편리합니다.
* 비교 연산자 \=\=, \=\=\=
		var one= 1, oneString = '1' , t = true;

        console.log(one == oneString);
        console.log(one == t);
        console.log(oneString == t);
        
        console.log(one === oneString);
        console.log(one === t);
        console.log(oneString === t);
* 원시값/복합 객체의 저장, 복사, 그리고 비교
	* 복사
    		var p = 1;
            var copyOfP = p;
            p = 3;
            console.log(copyOfP);
            
            var myObject = {};
            var copyOfMyObject = myObject;
            myObject.foo = 'bar';
            console.log(copyOfMyObject.foo);
	* 원시값의 비교    	
            var p1 = 10;
            var p2 = 10;
            var p3 = new Number('10');
            var p3_1 = Number('10');
            var p4 = p3;
            
            console.log(p1 === p2);
            console.log(p1 === p3);
            console.log(p3_1 === p3);
            console.log(p1 === p3_1);
            p4=10;
            console.log(p4 === p3);
    * 복합 객체의 비교
    		var objectFoo = { smae : 'same' };
            var objectBar = { smae : 'same' };
            
            console.log( objectFoo === objectBar );
            
            var objectA = { name : 'name' };
            var objectB = objectA;
            
            console.log( objectA === objectB );
* 객체 속성 접근방법
	* object['property_name']
    * object.property_name
    		var obj = {
            	name : 'MyObject'
                };
            var a = 'name';
            console.log(obj.name);
            console.log(obj["name"]);
            console.log(obj[a]);
* 함수는 1급 클래스이다.  
>변수, 배열, 객체에 저장될 수 있다는 뜻이다. 또한 함수에 전달될 수도 있고 함수에서 반환될 수도 있다. 그리고 함수는 객체이기 때문에 속성도 가지고 있다. - "자바스크립트를 깨우치다" 중에서

	* this
	* arguments
	* arguments.callee
	* Hoisting : 함수 선언문 먼저 해석하고 Excuete context에 추가
			var is_android = true;
            if(is_android) {
               function foo() {
                  console.log('I am Android');
               }
            } else {
               function foo() {
                  console.log('I am NOT Android');
               }
            }
            foo();
	* 재귀
	* 클로져

* 기타 팁
	* `var a = (isTrue == true)? 'This is true':'This is false'`;
    * `var a = b || {}`
    * `var a = callback && callback();`

## 4. Titanium UI & Alloy View
Alloy View와 Style을 가지고 설명하며 진행, 강사의 시연을 먼저 보고 수강자들의 실습을 진행.
* OS별 버전별 UI의 살펴보기
* View 계층구조
* positioning 앞서 TSS 파일 이해하기
	* 상속 안됨
* positioning & size
	* left, top, right, bottom
* Ti.UI.SIZE, Ti.UI.FILL
	* Buttons, labels, images, text fields and areas = Ti.UI.SIZE
	* Windows, views, tables, webviews = Ti.UI.FILL
	* Table rows = FILL for width and SIZE for height
* 단위
	* px, dp/dip, mm, cm, in, %
	* `<property name="ti.ui.defaultunit">system</property>`
* layout
	* vertical
    * horizontal
    	* horizontalWrap 속성
* sibiling 간의 순서
	* 기본 및 zIndex
* view 관련 참고 자료
	* 정영석님의 Alloy 코드로 살펴본 UI 기초 지식 : http://tidev.kr/t/titanium-alloy-ui/205
    * TCD 교육 자료 : https://github.com/appcelerator-training/tcd_training

## 5. Titanium UI & Alloy Controller
* Event
	* UI 컴포넌트의 event
* 상속
	* `exports=baseController = 'parentControllerName'
	
    
## 6. Cross Platform의 대응
http://docs.appcelerator.com/titanium/3.0/#!/guide/Alloy_Styles_and_Themes-section-35621526_AlloyStylesandThemes-StylePriorities
* files
	* image : 각 os별로 native와 동일
    * folder로 구분
* View 와 Style
	* platform, formfactor 구분자
* in Controller
	* Conditional Code
    * OS_ANDROID : true if the current compiler target is Android
    * OS_BLACKBERRY: true if the current compiler target is BlackBerry
    * OS_IOS : true if the current compiler target is iOS
    * OS_MOBILEWEB : true if the current compiler target is Mobile Web
    * OS_TIZEN : true if the current compiler target is Tizen
    * ENV_DEV : true if the current compiler target is built for development (running in the simulator or emulator)
    * ENV_TEST : true if the current compiler target is built for testing on a device
    ENV_PRODUCTION : true if the current compiler target is built for production (running after a packaged installation)
    
## 7. Widget 사용하기
- [Alloy Love](http://alloylove.com/) 사이트에서 위젯을 다운로드 받는다.
- Alloy/widgets 폴더에 넣는다.
- config.json 에 위젯의 의존성(이름과 버전)을 기술한다.
		"dependencies": {
            "com.appcelerator.acslogin" : 1.0
        }
- **위젯 사용하기**
```
<Widget id="loginWidget" src="com.appcelerator.acslogin"/>
```

## 8. Module 사용하기
- 타이타늄에서 제공하는 기본 모듈에 원하는 기능이 없을때 혹은 성능이 안나올때..
- 대표적인 사례,
  - 안드로이드 애니메이션 느리다.
  - 멀티 셀렉트 이미지 픽커
- 각 프로젝트를 빌드해서 moduels 폴더에 넣는다.
- `reauire('module name')` 구문을 통해 모듈을 불러온다.
- **모듈링크**
  1. https://github.com/billdawson/ti-android-animation
  2. https://github.com/amano/TiELCImagePicker

### Tip
* 단축키
    * view, style, controller 이동 단축키 : cmd+shift+v,s,c