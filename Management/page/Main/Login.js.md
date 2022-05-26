## 설정
- #### dispatch 사용 (useDispatch)
- #### id (useState 기본값 "")
- #### password (useState 기본값 "")
- #### error (useState 기본값 {type : "", message : ""})
- #### navigate 사용 (useNavigate)
- ### handleChange()
	- #### event의 주체가 id인지, password인지에 따라서 setState 함수를 정의, setState를 사용해 그 주체의 state의 값을 지정 (event.target)
- ### login()
	- #### 별 다른 전환이 일어나지 않게 함(event.preventDefualt)
	- #### id값이 공백이거나 pw값이 공백인 경우 에러메시지를 표출 (setError)
	- #### 값이 정상이면 로그인하여 토큰 가져오기를 시도하고, 토큰이 유효하다면 메인페이지로 이동한다 (authChangeFieldDispatch, setError)
	- #### 정의되어 있는 시간이 지나면 자동으로 토큰이 만료되며 초기화면으로 돌아간다(setTimeout, navigate, popupContentUpdateDispatch, authChangeFieldDispatch)
	- #### 에러 발생시 에러메시지를 표출해주고 만약 네트워크 에러라면 얼럿으로 표출해준다. (setError, authChangeFieldDispatch, alert, navigate)
- ## return ()
	- #### 로그인 페이지 표출 (로그인 폼, 회원가입 페이지 이동 버튼 등)