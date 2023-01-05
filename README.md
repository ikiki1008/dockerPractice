# dockerPractice
<br>

### 도커 이미지  
도커 이미지는 컨테이너를 만드는 데 사용되는 읽기 전용 템플릿, 컨테이너 실행에 필요한 파일과 설정값 등을 포함하고 있는 도커파일을 만든 후 dockerfile을 빌드하여 이미지를 만든다


### 도커 컨테이너
도커 이미지를 실행한 상태
이미지로 컨테이너를 생성하면 이미지의 목적에 맞는 파일이 들어있는 파일 시스템과 격리된 시스템 자원 및 네트워크를 사용할 수 있는 독립된 공간이 생성됨
이것을 도커 컨테이너라고 한다.

![image](https://user-images.githubusercontent.com/80104121/210305597-70fa327c-159e-4c7a-a7ca-ddd50559d7d5.png)
![image](https://user-images.githubusercontent.com/80104121/210305671-f980e838-45ec-4b41-bdf5-c0bd9c1b2deb.png)

<br><br><br>

## 도커 이미지 생성 및 컨테이너 생성 

도커 이미지 생성시 도커 파일이 있는 디렉토리에서 생성해야함

1. 도커 파일 ssh 이용하여 git clone 후 파일 생성
> https://gitlab.drimaes.com/kms/build-docker 사이트 참조

2. sudo docker build --force-rm -t ubuntu-18.04 --build-arg USERNAME=mia --build-arg PASSWORD=0714 --build-arg USERID=1000 --build-arg GROUPID=1000 .
   명령어를 이용하여 image 생성. image 이름은 ubuntu 18... 유저아이디와 그룹아이디는 1000으로

3. 이미지가 완료되면 컨테이너 만들기 (참고로 만들어진 컨테이너를 이미지로 다시 변경하여 배포할수도 있다) 
   sudo docker run -it -v /home/mia/Develop/la-3.4.1:/home/mia/workspace/ --name la-3.4.1 ubuntu-18.04
   
   경로는 home/mia/Develop/la-3.4.1 파일안에 컨테이너를 만들고 home mia workspace 경로를 공유해서 이 컨테이너 파일을 만들면 workspace 경로에도 같이 만들어질수 있도록 한다. 컨테이너 이름은 la 3.4.1 우분투 이미지를 사용해서 만듬
   
 
 
 <br><br>
 
 


### 관련 명령어
> -도커 시작 시 docker start testA -> docker attach testA<br/>
반드시 start 시켜 주고 난 후 attach 하기<br/> 
-docker ps -a<br/> 
현재 컨테이너 목록 보여주는 명령어<br/> 
-docker images<br/> 
현재 도커 이미지 목록<br/> 
-su mia || su root<br/> 
도커 내에 진입하는 명령어<br/> 
-ctrl+pq<br/> 
도커를 종료시키지 않고 잠시 정지시켜 빠져나오는 명령어<br/> 
-docker ps -a<br/> 
전체 컨테이너 목록 확인<br/> 
-docker ps<br/> 
현재 실행중인 컨테이너 목록 확인<br/> 
-docker images<br/> 
도커 이미지 목록 확인 

> 2)실행된 컨테이너에 git 설치<br/>
#apt 갱신<br/>
$apt update<br/>  

> #git 설치<br/>
$apt install git<br/>
<br><br>  
   

