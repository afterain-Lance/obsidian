## 설정
- #### filteredItems ( useState 기본값 \[])
- #### isDesktop ( useMediaQuery )
- #### isDesktop의 값이 참 / 거짓인지에 unitPerPage(페이지 당 디바이스 수) 값 결정
	##### 				참일 경우 => 40으로 설정
	##### 				거짓일 경우 => 20으로 설정 ( ? 문법 )
- #### deviceArray는 devices로 부터, focusedCategory는 focusedCategory로 부터, focusedPage는 focusedPage로 부터 상태값을 가져옴 ( useSelector )
- #### localStorage에서 "userIdx" 항목을 idx 변수에 저장 ( localStorage )
- #### navigate 활성화 ( useNavigate )
- #### dispatch 활성화 ( useDispatch )
- #### getConnectIndex이라는 함수를 만들어서 
####   제품 리스트를 업데이트 잘 할 수 있도록 함.
- #### getHome이라는 함수를 통해 deviceArray의 길이가 1 미만일 경우 api 호출하여 deviceArray에 저장
- ### 카테고리 / 디바이스의 갯수 / 디바이스 목록페이지 번호의 변화가 생기면  HomeRendering을 호출 ( useEffect )
### HomeRendering
- ##### focusedCategory에 따라 필터 O, deviceArray가 조건식을 충족하면 <[[Item.js|Item]] /> 리턴
	#### focuesdCategory의 값이 "⌘"일 경우 =>필터x, 조건식 : index가 한 페이지당 유닛 수 x (현재 페이지 +1) 보다 작으며 index가 현재 페이지 x 페이지당 유닛 수 이상이면 true, 아니면 false
	#### focuesdCategory의 값이 특정 카테고리일 경우 =>조건식 : deviceArray 속 device의 값이 카테고리와 일치하며 index가 한 페이지당 유닛 수 x (현재 페이지 +1) 보다 작으며 현재 페이지 x 페이지당 유닛 수 이상이면 true, 아니면 false ( array.map, if )

## return () 
- #### <[[Toolbar.js|ToolBar]] type = "home"/> 표출
- #### <[[CategoryBar.js|CategoryBar]] /> 표출
- #### filterdItems 길이가 1 미만인 경우에만 로딩중을 표시하기 위한 <Loading /> 출력
- #### 디바이스 갯수에 따른 페이지 생성을 위한 <PageCountBox /> 출력