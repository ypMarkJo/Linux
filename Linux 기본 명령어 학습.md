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

### 7. Hard & Soft(symbolic) Link
![image](https://user-images.githubusercontent.com/80379900/120616462-38ad0880-c494-11eb-8884-6a77afa45428.png)
- 사용자에게 보여지는 파일 저장의 형태가 Link File형태이고 하드에 직접 저장되는 게 Filesystem인데<br> 둘은 공통의 인수인 inode를 통해
맵핑된다.
#### 1) 하드링크
![image](https://user-images.githubusercontent.com/80379900/120617215-dc96b400-c494-11eb-9363-00a79812b95e.png)
- 기본적으로 파일시스템에 저장될 때 한 inode당 참조값을 하나를 가지지만 그림과 같이 복사본을 원본의 inode로 하드링크하는 경우 원본과 복사본의 개념이 없어지며 데이터 조작이 모두 영향을 받는다. 단, 삭제는 참조값을 1을 빼줌으로써 각자 삭제된다.
- 하드링크는 파일에만 설정할 수 있으며, 디렉토리에는 설정할 수 없다.<br>

#### 2) 소프트링크
![image](https://user-images.githubusercontent.com/80379900/120727252-02fc3400-c515-11eb-9198-85591d79a432.png)<br>
- 오픈소스 진영에서 많이 사용되는 링크 방식으로 간단하게 말하면 바로가기를 생성하는 것이 소프트 링크가 된다.
- 오픈소스 진영에서는 version정보가 매번 패치넘버, 마이너버그와 같이 변동되는 파일이름 속 가변인자를<br> 추적하기가 힘드므로
그림과 같이 library.so라는 소프트링크를 설정해서 버전이 바뀔 때마다 새로 링크를 여기에 걸어준다.<br> 그러면 개발자들은
일일이 파일버전을 추적할 필요없이 최신화된 library.so만 이용하면 된다.

#### 3) 링크 구현
- 소프트 링크의 구현<br>(상황: 라이브러리 0.1이 배포되었다가 수정 후 0.2버전이 출시되었을 때 소프트 링크를 통해 버전없이 library.so만 이용)
> ln -s source target

![image](https://user-images.githubusercontent.com/80379900/120728110-27591000-c517-11eb-9035-802e29828c28.png)<br>
![image](https://user-images.githubusercontent.com/80379900/120728135-3344d200-c517-11eb-939a-6f2b6876cf1a.png)<br>
![image](https://user-images.githubusercontent.com/80379900/120728148-3a6be000-c517-11eb-87c1-97f370a925ae.png)<br>
![image](https://user-images.githubusercontent.com/80379900/120728164-43f54800-c517-11eb-9c76-b7bac1268fe9.png)<br>

- 하드 링크의 구현<br>
> ln source target<br>

![image](https://user-images.githubusercontent.com/80379900/120728448-e9a8b700-c517-11eb-9bb2-0a9fed7da218.png)
![image](https://user-images.githubusercontent.com/80379900/120728437-e31a3f80-c517-11eb-9920-0fe804d98910.png)
  - 맨 앞의 inode가 myfile,file1에서 서로 같은 걸 가르키고 있다.
