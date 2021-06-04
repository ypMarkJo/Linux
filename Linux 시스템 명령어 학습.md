### 1. tar 명령어
#### 1)압축만들기
> tar cvfz (압축파일이름).tar.gz ./(압축할 대상) [띄워쓰기로 대상 열거 가능] 

![image](https://user-images.githubusercontent.com/80379900/120735089-ee279c80-c524-11eb-8434-c07925b26dc0.png)
- 경로에 있는 모든 파일을 압축하려면 * 를 붙여주면 된다.<br>

![image](https://user-images.githubusercontent.com/80379900/120735146-08fa1100-c525-11eb-8be1-71808d3f6391.png)
![image](https://user-images.githubusercontent.com/80379900/120735236-347cfb80-c525-11eb-8c2c-5cb29e1d468d.png)<br>
**cvfz : create/vf/gzip**

#### 2)압축풀기
> tar xvfz (압축파일)<br>

![image](https://user-images.githubusercontent.com/80379900/120735541-bf5df600-c525-11eb-8211-68cfd660c242.png)<br>
**xvfz: extract/vf/gzip**


### 2. sudo 명령어(root권한을 부여)
![image](https://user-images.githubusercontent.com/80379900/120736097-9b4ee480-c526-11eb-834e-a346a51ae473.png)


### 3. chown 명령어
- 소유자를 변경할 수 있는 명령어.
> sudo chown (사용자):(소속그룹) (대상)<br>

![image](https://user-images.githubusercontent.com/80379900/120736750-c5ed6d00-c527-11eb-824c-fe9301d86e9d.png)

### 4. find 명령어
- 설정된 조건과 일치하는 경로를 찾아주는 명령어
> find (범위경로) (검색옵션) (검색조건)<br>
 
![image](https://user-images.githubusercontent.com/80379900/120737395-f681d680-c528-11eb-9150-32914db63c17.png)

### 5. which 명령어
- 명령의 위치를 찾아주는 명령어.<br>
![image](https://user-images.githubusercontent.com/80379900/120737778-ace5bb80-c529-11eb-8866-58671772252c.png)

### 6. top 명령어
- 운영중인 시스템의 사용상황을 조회하는 명령어<br>

![image](https://user-images.githubusercontent.com/80379900/120738080-2c738a80-c52a-11eb-8481-dbd355e4e0ed.png)

### 7. w/who 명령어
- 접속한 계정정보와 IP를 조회하는 명령어<br>

### 8. nslookup : 도메인이나 ip를 입력하면 그 정보를 보여줌

### 9. ps 명령어
> ps -ef [전체 프로세스 출력]<br>
> ps -ef | grep (찾으려는 프로세스 이름)[특정 프로세스 출력]<br>
> kill -9 (죽이려는 프로세스 아이디) [특정 프로세스 종료]<br>

![image](https://user-images.githubusercontent.com/80379900/120746060-61d3a480-c539-11eb-933a-fbb49533958b.png)

### 10. adduser 명령어
> sudo adduser (새 계정이름) [새로운 계정을 추가한다.]<br>
> su -l (이용할 계정이름) [새 계정으로 이동한다]<br>
> sudo deluser (삭제할 계정이름) [계정을 삭제한다.]<br>
