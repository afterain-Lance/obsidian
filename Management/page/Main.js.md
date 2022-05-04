## 설정

- #### location(useLocation)
- #### isibleMenubar 상태값 조회(useSelector)
- #### profileState(useState 기본값 false)
- #### isVerified auth에서 조회 (useSelector)

- #### dispatch 활성화(useDispatch)

- #### esc(Escape) 누름을 감지 (useKeyPress)
- #### esc를 누르면 profileState값을 false로 변경 (useEffect)

- #### isDesktop에 현재 가로 길이가 769 이상(참) / 미만(거짓) 인지 구별하여 값을 넣음 (useMediaQuery)
- #### isDesktop의 값에 따라서 menubar의 출력 유무를 결정 (참 => display = flex / 거짓 => display = none) (dispatch)

- #### location.pathname (현재 주소)를 /로 나눈 두번째 배열의 값(device, admin)에 따라 admin, home을 표출할지를 결정하여 표출(useEffect)

- #### {isVerified가 참이 아닐경우 => 주소가 "/" 이면 <[[Login.js|Login]] /> 출력
	#### 								 주소가 "/signup" <[[Signup.js|Signup ]]/>출력
	#### 																					 (Routes)
	#### 							isVerified가 참일 경우 => [[메인페이지|접속 후 페이지]] 출력} (? 문법)
