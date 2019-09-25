## 라즈베리 파이로 AP 만들기

### 0. Raspbian 이미지 만들기
참고 (https://www.raspberrypi.org/documentation/installation/installing-images/README.md)
- Raspbian Buster Lite 이미지 다운로드
- balenaEtcher로 img를 sd카드로 만듦

### 1. 무선랜 접속 및 ssh 실행
참고 (https://m.blog.naver.com/PostView.nhn?blogId=specialist0&logNo=221232983680)
- SD카드 boot파티션에 빈 ssh 파일 만들기 (내용x 확장자x)
- wpa_supplicant.conf 파일 만들고 무선랜 정보 설정
~~~
country=GB
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
ssid="NETWORK_NAME"
psk="PASSWORD"
key_mgmt=WPA-PSK
}
~~~
** 한 번 SD카드를 넣고 부팅하면, ssh 파일과 wpa_supplicant.conf 파일은 삭제됨 **

#### 라즈베리파이 ip 찾기
- nmap 설치 후 `nmap -sn 172.30.1.0/24` 실행해서 ip scan

#### ssh 접속 `ssh 172.30.1.43 -l pi` 기본 비밀번호는 raspberry

### 2. AP 만들기
참고 (https://dejavuqa.tistory.com/284)
- 
