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




1) ubuntu 이미지 실행  
#ubuntu 이미지 다운로드  $ docker pull ubuntu  

#my-ubuntu라는 컨테이너명으로 실행 (실행하자마자 bash 터미널에 연결 유지하기)  
$docker run -it --name my-ubuntu ubuntu bash  
<br><br>  

2) 실행된 컨테이너에 git 설치<br/>  
#apt 갱신<br/>  
$apt update<br/>  

#git 설치  
$apt install git  
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
