## 설정
- #### localStorage에서 deivceId 라는 키값을 가진 항목의 value값을 id 변수에 불러오기
- #### navigate 사용 (useNavigate)
- #### dispatch 사용 (useDispatch)
- #### localStorage에서 location 라는 키값을 가진 항목의 value 값을 location 변수에 불러오기
- #### onRebootButton / onUpdateButton  / onShutDownButton / onClickSettingButton / onClickDataDownload  / onClickPositionSettingButton 정의
- #### types 객체로  toolbar의 종류를 나눌 수 있게 정의
   #### home : <HomeToolBar />
   #### device : <DeviceToolBar /> 
## return ()
- #### types\[type] ? 을 통해 있는지 없는지에 따라서 toolbar의 출력 유무를 결정
   #### DeviceToolBar (업데이트, 재부팅, 다운로드, 설정, 액츄에이터 설정, 좌표값 수정)
   #### HomeToolBar (완료 / 편집) \[디바이스의 추가/제거]
   #### SettingToolBar (설정)