### 1. pwd 
- 현재 위치 확인.
### 2. ls(기본) or ls -l(상세) or ls -al(숨겨진 파일과 권한까지 ll명령어도 동일)
- 디렉토리 정보 조회, 리눅스에서는 파일이 .으로 시작하면 숨김파일이란 뜻.<br>
![image](https://user-images.githubusercontent.com/80379900/120600118-5c1b8780-c483-11eb-9fb6-f2a348ddf8c3.png)<br>
  (권한 정보)  (소유자) (소속그룹) (용량) (최종 수정일) (파일/폴더 이름)
![image](https://user-images.githubusercontent.com/80379900/120601126-86217980-c484-11eb-9ca6-6d6b4e1954ec.png)<br>
![image](https://user-images.githubusercontent.com/80379900/120605942-9b4cd700-c489-11eb-98eb-b53e5067f0a5.png)
![image](https://user-images.githubusercontent.com/80379900/120605998-aacc2000-c489-11eb-9979-d5a767b03099.png)<br>
-> 유저에게 test.c 파일의 실행권한을 준다.

### 3. mkdir/touch/rm 명령어(make directory/remove)
> mkdir (폴더이름) [폴더 생성]<br>
> touch (파일이름) [파일 생성]<br>
> rm (폴더(-R)/파일 이름(-f)) [삭제]<br> 

### 4. cd명령어(change directory)
![image](https://user-images.githubusercontent.com/80379900/120606831-90467680-c48a-11eb-88b9-c25708b32e22.png)

### 5. mv명령어(move)
> mv (보내려는 것) (보내려는 곳) 
- 파일을 이동시킬 수도 있지만 파일이름을 변경할 수도 있다.

### 6. cp명령어(copy)
> cp (복사할 것) (복사될 위치)
