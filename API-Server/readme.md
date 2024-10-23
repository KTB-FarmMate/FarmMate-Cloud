0. 자바 환경 만들기(jdk 설치)
	- `sudo yum install java-21-amazon-corretto-devel`
1. 깃 프로젝트 끌고 오기
	- `sudo git clone https://github.com/KTB-FarmMate/FramMate-API-Server`
	- `cd FarmMate-API-Server`
2. 스프링 폴더에 권한 주기
	- `sudo chmod +x gradlew`
3. 스프링 빌드하기
	- `./gradlew clean build -x test`
	- 빌드하면 현재 경로에서 `build/libs` 안에 빌드된 .jar 파일이 있을거임
	- 파일 옮기기 `cp farmmate-0.0.1-SNAPSHOT.jar ~/`
4. 도커 파일 만들기
   	- `cd ~`
	- `sudo vi Dockerfile`
6. 이미지 빌드하고 실행하기
	- `docker build -t testspring:latest .`
	- `docker run -d -p 8080:8080 testspring:latest --name testSpring`
