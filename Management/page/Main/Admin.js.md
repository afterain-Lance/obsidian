## 선언
- #### allDeviceList, renderDeviceList, limit, page, sortCondition (useState)

- ### serialNumberInfo( props )
	- #### allDevicelist 변수 선언 (useState 기본값 \[]) 
	- #### renderDeivceList 변수 선언 (useState 기본값 \[])
	- #### limit 변수 선언 (useState 기본값 10)
	- #### page (useState 기본값 0)
	- #### sortConditon (useState 기본값 '')
	- ### useEffect(limit,allDeviceList,sortCondition)
		- #### sortedDevicelist에 allDeviceList.concat(\[]) 저장
		- #### sortCondition값이 비어있지 않다면 : 이해가 되지 않음
				(addSerialNumber로 대체됨에 따라서 사용처가 없다고 판단됨)
	- ## return ()
		- #### <[[addSerialNumber.js|addSerialNumber]] /> 출력