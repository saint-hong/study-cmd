# 커맨드 명령어
- 기본 명령어
- 유용한 명령어

## 1. 기본 명령어

### 1-1. dir
- 디렉토리의 목록

```python
dir : 현재 디렉토리의 파일 목록
dir .. : 상위 디렉토리의 파일 목록
dir ..\.. : 상위의 상위 디렉토리 파일 목록
dir ..\all_data\ : 상위의 디렉토리 목록에서 all_data 디렉토리의 파일 목록
```

### 1-2. cd
- 디렉토리 이동

```python
cd 010_my_summary : 현재 디렉토리에서 010_my_summary 디렉토리로 이동
cd .. : 상위 디렉토리로 이동
cd ..\.. : 상위의 상위 디렉토리로 이동
```

### 1-3. copy, move
- 파일 복사
    - copy <복사대상의 경로+파일이름> <복사 위치의 경로+파일이름>
    - 복사 할 때 파일명을 바꿔도 된다.
- move : 파일 이동
    - copy와 같은 방식
    - move 를 현재 디렉토리로 지정해주면 파일의 이름을 바꿀 수 있다.

```python
copy ..\all_data\wine_data\wine_red.csv .\wine_red.csv : 상위디렉토리->all_data->wine_data->wine_red.csv 파일을 현재 디렉토리에 복사
```

### 1-4. cls
- 커맨트 창의 명령-실행 내용 지우기
    - 또는 화면을 위로 스크롤하면 마지막 명령줄이 첫줄이 된다.

### 1-5. type
- txt 파일을 화면에 보여준다.

### 1-6. exit
- 명령프롬프트 창 닫기

### 1-7. 실행 중단/일시정지
- ctrl+C

### 1-8. 명령어 히스토리
- 위쪽 방향키 : 이전에 실행한 명령어
- 아래쪽 방향키 : 이전에 실행한 명령어에서 다음 명령어 검색

## 2. 유용한 명령어

### 2-1. findstr
- 어떤 명령어의 실행결과에서 특정한 문구를 검색하여 그 실행결과만 따로 보여준다.
    - <명령어> | findstr <검색할 문구>
    - | 는 앞의 내용을 뒤로 넘겨주는 기능

#### 드라이버 목록에서 볼륨 관리자 드라이버만 검색

```python
driverquery : 내 컴퓨터에서 사용하고 있는 모든 드라이버의 목록
```
![pic_1.png](./images/pic_1.png)

```python
driverquery | findstr volmgr
```
![pic_2.png](./images/pic_2.png)

### 2-2. ipconfig
- 컴퓨터의 IP 구성정보 확인
    - 실제로 내 컴퓨터가 사용하고 있는 IP
    - 공유기에서 할당하는 IP
- 공인 IP가 아니다. : 정확한 의미 확인할 것

```python
ipconfig
```
![pic_3.png](./images/pic_3.png)

### 2-3. netstat
- 컴퓨터에 연결되어 있는 모든 IP와 사용중인 포트 확인
    - 로컬주소 : 내 컴퓨터
    - 외부주소 : 상대방의 컴퓨터나 서버의 주소
    - 주소의 콜론 뒤 숫자 : 포트넘버
    - 상태 : LISTENING, ESTABLISH, TIME WAIT, FIN WAIT 2
- 상태
    - LISTENING : 윈도우에서 프로그램이 열고 있는 포트를 통해서 데이터가 들어오기를 기다리고 있는 상태
    - ESTABLISH : 로컬주소와 외부주소에 나와 있는 대상이 서로 데이터를 주고 받고 있는 상태
    - TIME WAIT : 로컬주소와 외부주소에 나와 있는 대상이 서로 데이터 교환을 종료한 상태
    - FIN WAIT 2 : 로컬주소와 외부주소에 나와 있는 대상이 서로 데이터 교환을 종료 중인 상태

```python
netstat
```
![pic_4.png](./images/pic_4.png)


### 2-4. 현재 사용중인 포트와 어떤 프로그램이 사용중인지 확인
- 현재 사용중인 포트와 프로그램 PID 값 확인
    - 맨 뒤의 숫자가 프로그램의 PID 값

```python
netstat -ano | findstr "ESTABLISHED"
```
![pic_5.png](./images/pic_5.png)

- tasklist에서 프로그램 PID 값 조회

```python
tasklist /fi "pid eq 22256"
```
![pic_6.png](./images/pic_6.png)

### 2-5. tasklist
- 작업관리자
    - 현재 실행중인 프로그램 확인 

```python
tasklist
```
![pic_7.png](./images/pic_7.png)

### 2-6. systeminfo
- 컴퓨터의 기본정보, 메모리, 프로세서, 하드웨어 정보 등을 확인

```python
systeminfo
```
![pic_8.png](./images/pic_8.png)

### 2-7. 파일목록을 txt 파일로 만들기
- 디렉토리의 파일목록을 txt 파일로 만들어 준다.

```python
dir ../b > list.txt : 상위 디렉토리의 파일목록을 list.txt 파일로 만들어 현재 디렉토리에 저장
```

































