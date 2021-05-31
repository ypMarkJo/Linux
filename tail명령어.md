## 리눅스 기본 명령어 : tail
> tail명령어는 파일의 마지막 행을 기준으로 지정한 행까지의 파일내용 일부를 출력한다. 기본값으로 마지막 10줄을 출력해준다.
> 반대의 경우 head 명령어가 있고 앞부분 10줄을 출력한다. tail은 실시간으로 최근 10개 건의 데이터를 보여주므로 
> 로그나 오류를 보는데 유용하다.<br>

![image](https://user-images.githubusercontent.com/80379900/120171666-3dc44a80-c23d-11eb-9ba1-6df4cb0e9af6.png)

> 명령어를 옵션없이 입력하면 파일의 끝부터 10개 행을 표준출력한다.여러개의 파일이 입력된 경우 파일별로 각각 10개 행씩 출력한다.
> 파일명이 없으면 표준입력을 읽어들인다.

![image](https://user-images.githubusercontent.com/80379900/120171921-811eb900-c23d-11eb-8d1d-bd2676122272.png)

>디폴트 값이 아니라 지정한 행까지 출력을 할 경우 -n 옵션을 이용하여 아래와 같이 옵션 값을 입력한다.<br>
>반대로, 파일의 특정 행부터 마지막 행까지 출력하려면 '+'를 이용한다.

![image](https://user-images.githubusercontent.com/80379900/120172196-c0e5a080-c23d-11eb-9130-cf2203d6b4dc.png)

>행 단위 대신 byte를 기준으로 입력할 수도 있다.

![image](https://user-images.githubusercontent.com/80379900/120172476-0efaa400-c23e-11eb-8de5-59939e906e87.png)

>오류나 파일 로그를 실시간으로 모니터링할 경우에는 -f옵션을 사용한다. -f옵션을 사용할 경우 파일의 마지막 10줄을 출력하며<br>
>종료되지 않은 채로 표준입력을 계속 받아들인다.

![image](https://user-images.githubusercontent.com/80379900/120172728-4cf7c800-c23e-11eb-8f4c-7bad7486a4e6.png)

![image](https://user-images.githubusercontent.com/80379900/120172822-67ca3c80-c23e-11eb-9d59-b3b11b6a9603.png)
