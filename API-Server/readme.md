0. 자바 환경 만들기(jdk 설치)
	- `sudo apt update`
	- `sudo apt install openjdk-21-jdk`
1. 깃 프로젝트 끌고 오기
	- `sudo git clone https://github.com/KTB-FarmMate/FramMate-API-Server`
	- `cd FarmMate-API-Server`
2. 스프링 폴더에 권한 주기
	- `sudo chmod +x gradlew`
	- `sudo chown -R $USER:$USER /home/lyle/javaSpring_project/FramMate-API-Server\nsudo chmod -R 755 /home/lyle/javaSpring_project/FramMate-API-Server`
3. 스프링 빌드하기
	- `./gradlew build`
	- 빌드하면 현재 경로에서 `build/libs` 안에 빌드된 .jar 파일이 있을거임
	- 파일 옮기기 `cp farmmate-0.0.1-SNAPSHOT.jar ~/javaSpring_project`
4. 도커 파일 만들기
	- `sudo vi Dockerfile`

5. 뭔가 권한 주기(이미지 빌드에서 한번 막힘)
	- `sudo chown -R $USER:$USER /home/lyle/javaSpring_project/.java\nsudo chmod -R 755 /home/lyle/javaSpring_project/.java`
6. 이미지 빌드하고 실행하기
	- `docker build -t testspring:latest .`
	- `docker run -d -p 8080:8080 testspring:latest --name testSpring`
