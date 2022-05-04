## 설정
- #### headerType 초기화 (useState 기본값 "")
- ### useEffect ()
	- ##### url을 /를 기준으로 쪼개서 배열에 저장
	- #### url배열의 3번째 값을 통해 hederType의 값 초기화 (useState)
- #### navigate 사용 (useNavigation),
- #### dispatch 사용 (userDispatch
- #### state.devices에서 seletedDivces를 가져오기(useSelector, 구조 분해 할당)
- #### selectedDevice에서 id, device의 값을 따로 가져옴 (구조 분해 할당)
- #### localStorage에서 "location" 키 값을 가진 value를 location에 담기 (.getItem)
- #### deviceIconList에 여러가지 icon 담기
- #### deviceList에 표출할 디바이스 종류별 형식 담기
- ### useEffect ()
	- ### getDeviceData () 정의
		- #### localStorage에서 deviceId 라는 키값을 가진 value를 불러아 id에 담기
		- ### 아래의 명령어들을 실행 (try) 
			- #### manageAPI를 이용해서 device의 데이터들을 담아서 각 변수에 저장 (manageAPI.get)
			- ### 각 데이터들을 promise 객체에 담아서 데이터를 다 받아오면(.then)
				- #### 각 데이터들을 구조 분해 할당을 통해 각 변수에 저장
				- #### 액츄에이터 설정값 객체를 문자열로 변환 (JSON.stringify)
				- #### device 에 각 데이터들을 모아서 객체로 묶기 (Object.assaign)
				- #### dispatch를 이용해서 문자열로 변환한 설정값을 저장 (setSettingDispatch)
				- #### dispatch를 이용해서 현재 선택된 디바이스의 정보를 저장 (selectedDeviceDispatch)
		- ### try를 실행중 오류 ( e ) 가 발생한 경우 (catch)
			- #### 에러문구를 "데이터를 가져오는데 실패했습니다. 잠시후 다시 시도해주시기 바랍니다."로 수정후 errorHandler를 통해 팝업으로 에러 표출
	- #### getDeviceData 실행
- ### deviceScreenRendering ()
	- #### deviceList의 information\[선택한 디바이스의 종류]를 리턴
## return()
- #### device.information이 undifined일 경우 : <Loading /> 태그 출력
	#### 그렇지 않을 경우 :  디바이스의 정보와 아이콘, 장소 이름, 헤더의 액츄에이터 설정값을 담아서<[[component/header/Header.js|Header]] /> 출력
- #### 주소가 "/setting" 일 경우 : <ActuatorSetting /> 출력
   #### 주소가 "/position" 일 경우 :  <PositionSetting /> 출력
   #### 주소가 "/download" 일 경우 : <Download />출력
   #### 주소가 "/" 일 경우 deviceScreenRendering 실행
   (Routes) 	
   