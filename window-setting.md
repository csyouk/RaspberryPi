# Window setting for raspberry pi
- [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
- [Angry IP Scanner](http://angryip.org/)
- [윈도우-라즈베리 파이 연결](http://www.rasplay.org/?p=2804)

1. Putty를 다운로드 한다.
2. \[윈도우\]  제어판 > 네트워크 및 인터넷 > 네트워크 연결 > 로컬영역 연결 우클릭 > 상태 > 자세히 > IPv4내용을 기록.
  - 여기에서 IPv4의 주소는 호스트의 주소를 나타낸다.
3. 라즈베리파이의 부트코드가 들어가 있는 SD카드를 윈도우에서 열어서 `cmdline.txt`파일을 연다.
  - 파일을 열면 다음과 같이 되어있다.
```bash
dwc_otg.lpm_enable=0 console=ttyAMA0,115200 kgdboc=ttyAMA0,115200 console=tty1 root=/dev/mmcblk0p2 rootfstype=ext4 elevator=deadline rootwait
```
4. 이 부분에 ip정보를 추가한다.
  - `ip=169.254.177.2`
5. 이 단계 까지 끝났다면, 라즈베리파이는 `ip=169.254.177.2`의 정보를 가지고 있고, 호스트(PC)는 자신에게 할당된 ip주소를 가지고 있는 상태이다.
6. Putty에 접속한 후, 라즈베리 파이의 IP주소를 입력한 후  접속한다.
7. 보안과 관련된 경고는 무시한다.
8. `login as:` 라고 메세지가 뜨면 **`pi`**라고 입력한다.
9. `pi@169.254.177.2's password:`라고 나오면 **`raspberry`**라고 비밀번호를 입력한다.
10. 다음과 같은 메세지가 나왔다면, 성공.
```bash
Linux cs-custom 3.10.25+ #616 PREEMPT Mon Dec 23 18:13:02 GMT 2013 armv6l

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Jul 19 23:16:32 2015
pi@cs-custom ~ $ 
```
