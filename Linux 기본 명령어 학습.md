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


### 8.man 명령어
> man (명령어 이름) [명령어의 메뉴얼을 보여준다]<br>


![image](https://user-images.githubusercontent.com/80379900/120728963-f679da80-c518-11eb-8766-e7f13744f4db.png)
![image](https://user-images.githubusercontent.com/80379900/120728986-042f6000-c519-11eb-88e3-3f59d6126e6e.png)

### 9.cat 명령어
> cat (파일이름) [표준입력을 표준출력으로 바꿔줌.쉽게 말해 코드파일의 경우 모니터 화면에 코드를 띄워줌]<br>

**리눅스에서는 명령어에서 명령어를 연결시켜줄 수 있는데 이를 파이프 라인(pipeline)이라고 한다.**
![image](https://user-images.githubusercontent.com/80379900/120730037-8587f200-c51b-11eb-8ec7-bf3271496c9a.png)

- 표준출력의 방향을 모니터가 아니라 파일로: 즉, 복사를 하겠다.<br>
> cat source > target<br>

![image](https://user-images.githubusercontent.com/80379900/120730427-6c337580-c51c-11eb-999a-130460569014.png)

**+ >>이면 파일의 마지막입력에 이어서 복사시켜준다.**
![image](https://user-images.githubusercontent.com/80379900/120730850-5bcfca80-c51d-11eb-8bc1-34c44d5d77f5.png)

### 10. head/tail 명령어

> head[or tail] (파일이름)<br>

- 파일의 처음 10줄(default)[tail은 끝에서 10줄]을 출력하는 명령어.
> tail -f (파일이름) 

- 추가될 때마다 보여줌.(로그를 보는데 유용)

### 11. grep 명령어

> grep (문자열) (파일이름)<br>
- 문자열이 들어있는 내용을 찾아주는 명령어.<br>
![image](https://user-images.githubusercontent.com/80379900/120733155-8f145880-c521-11eb-91e9-3acc94e80b9d.png)
![image](https://user-images.githubusercontent.com/80379900/120733186-9cc9de00-c521-11eb-9f19-aeda1adedaf8.png)

> grep -H (문자열) (파일이름)<br>
- 어떤 파일인지를 찾아줌.<br>
![image](https://user-images.githubusercontent.com/80379900/120733554-693b8380-c522-11eb-8dc0-7e0a56db311e.png)
![image](https://user-images.githubusercontent.com/80379900/120733664-912ae700-c522-11eb-8e9e-d1163b7fa7dc.png)

### 12. less 명령어
- 파일을 열고 내용을 볼 수 있는 텍스트뷰어 기능.
![image](https://user-images.githubusercontent.com/80379900/120734206-7442e380-c523-11eb-83a4-85869e104b01.png)<br>
- 그림과 같이 서버에 장애상황이 발생해 1기가의 로그를 확인해야 한다면<> 또 그걸 원격으로 본다면 메모리가 2기가나 잡혀먹는다.<br>
만일 메모리가 위태위태한 상황이라면 장애상황의 로그를 보려다가 메모리 장애를 또 만들어낼 수도 있는 상황이다.<br>
이럴 때는 vi가 아닌 less명령어를 이용해 로그를 확인하면 메모리에는 딱 눈에 들어오는 만큼 <br>기껏해야 1KB만 메모리를 사용하므로
효율적이다.

