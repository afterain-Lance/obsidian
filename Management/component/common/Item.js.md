## 설정
- #### state.itemEditable 값  읽어와서 itemEditable에 닮기 (useSelector)
- #### navigate 사용 (useNavigation)
- #### dispatch 사용 (useDispatch)
- #### iconList 객체 초기화 {여러 아이콘들}
- #### item이라는 prop을 읽어와서 fd, ufd, id, locationInfo, mainType, serialNumber, subType, pastMinute에 각각 값 저장 (구조 분해 할당)
- ### selectItem(async)
	- ### 아래 명령어들 실행하기 (try)
		- #### localStorage에 deviceId 라는 키값을 가진 id 저장하기 (.setItem)
		- #### localStorage에 "location" 이라는 키값을 가진 locationInfo 저장하기 (.setItem)
		- #### dispatch를 통해 id값 저장하기 (selectedDeviceDispatch)
		- #### '/device/{id}'으로 이동하기 (navigation)
	- ### 만약 try를 실행하면서 오류(e)가 발생한경우 (catch)
		- #### dispatch를 이용해 isVerified의 값을 false로 바꿔주기 (authChangeFieldDispatch)
- ### deleteButtonOnclick (async)
	- #### LocalStorage에 deviceId 라는 키의 값을 가져와 id에 담아주기 (.getItem)
	- #### LocalStorage에 "location" 이라는  키의 값을 가져와 locationInfo 에 담아주기 (.getItem)
	- ### 아래의 명령어 실행 (try)
		- #### 'devices/{id}' 라는 주소를 가진 디바이스를 삭제하기 (await managerAPI.delete)
		- #### afterDeleteContent 에 type : "INFORMATION", title  : "삭제 성공", message : "{locationInfo} 제품을 삭제하는데 성공했습니다." 로 초기화
		- #### dispatch를 통해 afterDeleteContent 저장하기 (popupContentUpdateDispatch)
	- ### 만약 try를 실행하면서 오류(e)가 발생한경우 (catch)
		- #### e.errorString의 값을 "제품을 삭제하는데 실패했습니다. 잠시 후 다시 시도해주시기 바랍니다."로 초기화
		- #### e와 navigate, dispatch를 errorHandler에 담아 호출
- ### deleteItem ()
	- #### localStorage에 deviceId 라는 키값을 가진 id를 저장 (.getItem)
	- #### localStorage에 "location" 이라는 키값을 가진 locationInfo를 저장 (.getItem)
	- content라는 객체에 type, title, buttonState, message, buttonText, onClick을 지정해주기
	- content를 팝업에 사용 (popupContentUpdateDispatch)
## Return ()
- \<Link to={'.'} style={ itemEditable? styles.editableItemBox : styles.itemBox }
className="item-box"
onClick={ itemEditable? () => { deleteItem() } : async () => { await selectItem() } }
\<div className="device-icon">
{iconList[mainType]}\</div>
\<div className="item-name">{
locationInfo == ""
? "미지정"
: locationInfo
}
\</div>{
itemEditable ? false : mainType == "alsum" ? false
<>\<div>미세먼지 {Math.round(fd)}\</div>
\<div>초미세먼지 {Math.round(ufd)}\</div>
\</>
}
\</div>
{
itemEditabe
?\<div className="delete-button-box">
\<DeleteButtonIcon
width={36}
height={36}
/>
\</div> :
\<div className="device-state-box">
\<div style={{ backgroundColor: stateColor(pastMinute)}} className="device-state"/>
\</div>
}
\</Link>