---
title: "Integration Server 설치"
date: 2024-01-09 +0900
categories: [IntegrationServer, 설치 및 사용법]
tags: [EAI, webmethods]
---

# Integration Server  설치

> 이 포스트는 Free Trial 10.15 버전으로 진행합니다.
해당 평가판은 64비트 시스템에서만 사용 할 수 있으니 확인 부탁드립니다.
다운로드 및 설치 진행 전 회원가입을 먼저 진행해주세요.
[https://tech.forums.softwareag.com/](https://tech.forums.softwareag.com/)
> 

## Installer 다운로드 (Windows)

---

먼저 해당 사이트에 사이트에 접속하여 **Download free trial** 버튼을 누릅니다.

[webMethods Integration Free Trial Download](https://tech.forums.softwareag.com/t/webmethods-integration-free-trial-download/235077)

버튼을 누른 뒤 아래와 같은 화면이 나오면 정보를 모두 입력 후 **Submit** 버튼을 눌러줍니다.

![Untitled](/assets/img/Untitled.png)

Submit 버튼을 누르면 아래와 같은 화면이 나오는데 해당 화면에서
Windows Installer, Windows archive, License Key를 모두 다운로드 받아 주세요.

**email을 잘 입력 하셨다면 이메일로도 다운로드 링크가 전송됩니다**

![Untitled](/assets/img/Untitled%201.png)

- **Windows Installer**
    - Integration server 관련 제품 설치를 GUI로 도와주는 설치 도구입니다
    - Integration server, Designer, UM server 등 필요한 제품들을 선택 및 추가하여 커스텀설치 이미지를 만들 수 있는 기능도 제공되고 있습니다.
        - 이미지 생성 시 empower 계정이 있어야 합니다. 해당 포스트에서는 empower 계정이 존재하지 않는다는 가정 하에 진행하기 때문에 이미지 생성 부분은 생략하였습니다.
- **Windows archive**
    - 위에서 언급드린 설치 이미지입니다. 직접 이미지를 만들지 않고 평가판에서 사용할 수 있는 제품들로 이루어진 미리 만들어져 있는 이미지를 다운로드 받으셨다고 보시면 됩니다.
- **Lincese Key**
    - **Lincese Key** 입니다 해당 License Key는 무료평가판이므로 이 포스트에서 진행하고 있는 10.15 평가판 기준으로 2024년 4월 30일까지 유효합니다.
    - **Lincese Key**가 만료 될 경우 최신버전의 평가판을 다운로드 하여 해당 버전에 맞는 평가판 키를 받아서 사용 할 수 있습니다.

## 설치

---

> 다운로드가 완료 될 시 
Integration+v10.15+Free+Trial_Exp_04-30-2024.zip (**Lincese Key**) 의 압축을 먼저 풀어주세요.
> 

다운로드 받은 폴더에서 .exe로 끝나는 installer를 먼저 실행시키면 아래와 같은 프로그램이 시작 됩니다.

**Advanced Options**를 클릭 합니다.

![Untitled](/assets/img/Untitled%202.png)


<span style="color:red">1. **Images**를 클릭 합니다.</span><br>
<span style="color:red">2. **Use installation image**를 클릭 합니다.</span><br>
<span style="color:red">3. **Install from image**를 클릭 합니다.</span><br>
<span style="color:red">4. **Browse**를 클릭하여 설치 이미지 아카이브를 다운로드 받았던 경로로 이동하여 **.zip** 으로 되어있는 이미지 파일을 선택하여 주세요.</span>  

- **Scripts**로 설치를 진행 할 경우 선택해서 정보 입력 후 설치를 진행 할 수 있습니다
- **Image**로 설치를 진행 할 경우 선택합니다.
- **Caching** 이미지 파일의 경로를 텍스트 파일에 나열 후 다운로드를 받을 경우 선
택 합니다.
- **Logging** 설치 시 생기는 로그 파일의 경로를 직접 지정을 해 줄 수 있고, 설정
을 하지 않으면 default 위치로 생성됩니다.
- **Server** 설치 프로그램에서 지원하지 않는 제품에 대해 액세스 할 수 있는 기능
을 지원 합니다.

![Untitled](/assets/img/Untitled%203.png)

![Untitled](/assets/img/Untitled%204.png)

<span style="color:red">select 버튼을 눌러 선택 후 OK 버튼을 눌러 마무리 후 첫 화면이 나오면 next 버튼을 누릅니다.</span>

![Untitled](/assets/img/Untitled%205.png)

- **Installation directory**
    - 설치 할 디렉토리 입니다 기본 디렉토리를 원하지 않으시면 변경하셔도 됩니다
- **Start Menu group name**
    - 이 부분은 저도 확실하진 않으나 아마도 아래 이미지처럼 윈도우의 시작메뉴에서 서버 시작 아이콘들을 편하게 사용할 수 있게 만들어주는데 해당 그룹의 이름인것 같습니다
    
    ![Untitled](/assets/img/Untitled%206.png)
    

<span style="color:red">입력이 완료되면 **Next** 버튼을 누르면 아래와 같은 화면이 나옵니다.</span>

![Untitled](/assets/img/Untitled%207.png)

IS 제품 설치 목록입니다 저도 다 자세히는 알지 못하고 공식문서를 찾아봤으나 8.0 이후 문서를 찾지 못하였습니다 webmethods가 SoftWareAG사에 7버전 때 인수되어 8버전부터 출시 됐는지 8.0 문서에는 지금처럼 많은 제품이 있지 않아서 해당 제품 목록들의 대한 설명은 찾는데로 업데이트 하겠습니다.

일단 다음 포스트부터는 기본적인 사용법만 포스트 할 예정이라 필요한 부분만 설치하도록 하겠습니다. ( 지금 추가하지 않았더라도 이후에 추가적으로 설치가 가능하며 종속성이 있으면 자동으로 체크 됩니다 )

 

> 각 제품마다 라이센스가 존재하기 때문에 실무에서도 전부 다 설치 하는것이 아닌 필요한 제품마다 선택해서 설치하거나 필요한 제품들의 설치목록들을 이미지로 미리 만든다고 합니다.
> 

![Untitled](/assets/img/Untitled%208.png)

![Untitled](/assets/img/Untitled%209.png)

![Untitled](/assets/img/Untitled%2010.png)

![Untitled](/assets/img/Untitled%2011.png)

![Untitled](/assets/img/Untitled%2012.png)

<span style="color:red">체크를 다 한 뒤 **Next** 버튼을 누르면 업데이트 사항이 있는지 확인 후 아래와 같은 화면이 나옵니다</span>

![Untitled](/assets/img/Untitled%2013.png)

<span style="color:red">보시면 Fix가 붙어있고 View readmes를 클릭하여 변경 내역들에 대한 readme를 읽어 보실 수 있습니다.
**Next** 를 눌러 다음 화면으로 전환하면 아래와 같은 화면이 나옵니다</span>

![Untitled](/assets/img/Untitled%2014.png)

IS 서버는 처음 설정시 Administrator라는 계정이 기본으로 주어집니다.
이 때 해당 계정의 비밀번호를 설정 하는 화면이고 일반적으로 로컬에서 테스트용으로 사용하는 계정의 비밀번호는 manage로 설정을 많이 하고 실제 운영 환경은 당연히 다른 비밀번호로 사용 할 것 같습니다.

<span style="color:red">원하는 비밀번호를 입력 후  **Next** 버튼을 눌러줍니다.</span>

아래와 같이 IS (Integration Server) 서버 설정 및 라이센스키를 넣는 화면이 나옵니다.

- **Instance name**
    - IS서버 이름입니다
- **Secure port**
    - https로 연결할 수 있는 포트번호 입니다. ( 해당 포트를 사용중인지 확인해주세요 )
- **Primary port**
    - 기본 포트번호 입니다. ( 해당 포트를 사용중인지 확인해주세요 )
- **diagonostic port**
    - 긴급 포트번호 입니다 ( 해당 포트를 사용중인지 확인해주세요 )
- **Register Windows service/UNIX daemon for automatic startup ( 체크 X)**
    - 체크하면  OS 부팅시 IS가 데몬으로 백그라운드에서 자동으로 실행되는 것 같습니다
- **Host or IP address**
    - IP 주소 입니다 기본값은 “localhost” 입니다.
- **Install packages on this instance now**  ( 체크 O )
    - 제품 트리에서 선택했던 패키지를 IS instance에 install 합니다

![Untitled](/assets/img/Untitled%2015.png)

browse 를 눌러서 아래 그림처럼 처음 압축을 미리 풀어놓으라고 말씀드렸던 디렉토리로 들어가면
아래와 같이 여러 라이센스키들이 존재하는데  Integration Server 라이센스키를 선택하여 Select 합니다. 

![Untitled](/assets/img/Untitled%2016.png)

<span style="color:red">설정이 완료되셨다면 **Next** 를 누르면 아래 화면이 나옵니다.</span>

![Untitled](/assets/img/Untitled%2017.png)

데이터베이스 설정입니다. 설정해주셔도 되고 저는 테스트용이니 Embedded database로 체크 후 진행하겠습니다 .

<span style="color:red">설정을 다 하셨으면 **Next** 를 눌러주면 아래 화면이 나옵니다. </span>

![Untitled](/assets/img/Untitled%2018.png)

다음은 Platform Manager 설정입니다. 차후 Command Central 사용을 고려하지 않는다면 체크박스를 풀으라고 해서 저는 풀어주고 진행하겠습니다.

> **Software AG Command Central이란 무엇입니까?**
> 
> 
> Software AG Command Central은 Software AG 제품을 설치, 패치, 구성, 관리 및 업그레이드할 수 있는 도구입니다 . 데이터베이스 구성 요소를 생성합니다. 한 위치에서 원격으로 제품을 데이터베이스 구성 요소에 연결할 수 있습니다. Command Central은 브라우저 기반 사용자 인터페이스를 제공합니다. 터미널이나 사용자 정의 스크립트에서 작업을 원격으로 실행하는 명령을 사용하여 작업을 자동화할 수도 있습니다. Command Central은 Jenkins와 같은 지속적인 통합 서버와 Puppet 및 Chef와 같은 일반 구성 관리 도구를 지원합니다.
> 
> 이 **Command Central 릴리스는 릴리스 9.0 이상인 Software AG 제품을 관리할 수 있습니다** . Software AG는 안정성, 유용성 및 보안 강화는 물론 최신 기능을 활용할 수 있도록 제품과 함께 항상 최신 Command Central을 사용할 것을 권장합니다 . 이전 Command Central이 있는 경우 제품을 업그레이드하지 않더라도 최신 릴리스로 업그레이드할 수 있습니다. Command Central을 사용하여 관리할 수 있는 제품 목록 과 해당 제품의 각 릴리스에 지원되는 기능을 보려면 *Software AG Command Central 기능 지원 매트릭스를* 참조하세요 .
> 
> Command Central을 사용하면 기존 독립 실행형 제품 설치로 작업하거나 새 제품을 생성할 수 있습니다. DevOps 방식을 따르는 경우 제품 런타임의 소프트웨어 스택을 생성할 수 있습니다. 각 경우에 대해 제품(9.8 이상)을 설치하고 수정 사항(9.7 이상)을 설치할 저장소를 생성합니다.
> 
> 인터넷에 액세스할 수 있는 시스템에 하나의 Command Central을 설치합니다 . 이 Command Central은 Software AG 소프트웨어 다운로드 센터(SDC) 및 Empower 제품 지원 웹 사이트 에 연결되므로 라이센스가 있는 제품 및 수정 사항을 다운로드할 수 있습니다.
> 
> 개발 및 테스트 환경을 관리하기 위해 하나 이상의 Command Central 을 설치하고, 프로덕션 환경을 관리하기 위해 하나 이상의 Command Central 을 설치합니다. 이러한 Command Central 은 인터넷 액세스가 필요하지 않지만 관리하려는 제품을 호스팅하는 시스템에 액세스할 수 있어야 합니다.
> 
> 플랫폼 관리자 는 Command Central 의 에이전트입니다 . Platform Manager는 모든 Command Central 및 모든 제품 설치와 함께 설치됩니다 . 제품 설치에 대한 작업 요청을 제출하면 Command Central은 요청을 해당 설치의 플랫폼 관리자 에게 전달 하고 플랫폼 관리자는 작업을 실행합니다. 플랫폼 관리자는 항상 제품과 동일한 릴리스입니다.
> 

<span style="color:red">**Next** 를 눌러주면 아래와 같은 Universal Messaging 설정이 나옵니다</span>

> **Universal Messaging은 공용, 개인 및 무선 인프라 전반에 걸쳐 메시지 전달을 보장하는 메시지 지향 미들웨어 제품입니다**. Universal Messaging은 처음부터 다양한 네트워크를 통해 데이터를 전달하는 문제를 극복하기 위해 구축되었습니다. 웹 서버를 사용하거나 **방화벽 정책을 수정하지 않고도 보장된 메시징 기능**을 제공합니다.
> 

![Untitled](/assets/img/Untitled%2019.png)

![Untitled](/assets/img/Untitled%2020.png)

아까와 마찬가지로 Browser를 눌러서 UniversalMessaging 라이센스 키를 넣으신후 Select 를 눌러준 뒤 설정창을 다시 보겠습니다.

- **NHP interface binding**
    - NHP는 Universal Message에서 사용하는 HTTP를 이용한 프로토콜 인 것 같습니다 이 외에도
    NSP(소켓 프로토콜), NHPS(HTTPS 프로토콜), NSPS(SSL 프로토콜) ,SHM(공유 메모리 프로토콜) 등이 있습니다.
    - UM 서버가 어떤 IP와 연결을 수락할지 선택하는 항목인것 같습니다.
- **NHP interface port**
    - Realm server가 기동될때 사용 할 포트 번호 입니다.( 해당 포트를 사용중인지 확인해주세요 )
- **Realm server name**
    - Realm은 Universal messaging 단일 서버의 명칭입니다.
    - Realm 서버의 이름을 설정하는 항목 입니다.

<span style="color:red">Next를 누른 후 아래 그림에서 Install 을 눌러주세요.</span>

![Untitled](/assets/img/Untitled%2021.png)

![Untitled](/assets/img/Untitled%2022.png)

![Untitled](/assets/img/Untitled%2023.png)

> 설치가 끝나면 오류 메시지가 표시될 수 있습니다( **설치 중에 1개의 보고 또는 경고가 발생했습니다** )
평가판을 사용 하는데에는 아무런 영향이 없으므로 이 에러는 무시하셔도 됩니다. SoftwareAg 기술 커뮤니티에 공식적으로 올라온 내용을 확인하였습니다.
> 

## 실행 및 확인

---

설치가 잘 완료 됐다면 서버를 한번 기동 해보기 위해 서버실행 배치파일이 있는 곳으로 이동해보겠습니다. 
저의 경우 기본 디렉토리를 사용중이어서 SoftWareAg2 가 디렉토리지만 설치하실때 기본설정으로 하셨다면 SoftwareAG 일 것입니다

{ **Installation directory }/IntegrationServer/instances/default/bin**

![Untitled](/assets/img/Untitled%2024.png)

해당 디렉토리로 이동하여 startup.bat 배치파일을 실행시킵니다.

**중간에 제가 캡쳐를 못했는데 zulu … 뭔가가 나오면 확인 눌러주시면 됩니다 두번은 저도 안나와서 아마 포트를 열때 방화벽 허용을 하는지 물어보는것으로 추측됩니다.**

모두 실행이 끝나고 세션이 아래 화면처럼 물리고 로그가 아래처럼 떠있다면 잘 실행 된 것입니다.

![Untitled](/assets/img/Untitled%2025.png)

이제 관리 페이지에 접속 해 보겠습니다.

브라우저를 열고 localhost:{ primary portNumber } 를 쳐주시면 아래와 같은 화면이 나옵니다

![Untitled](/assets/img/Untitled%2026.png)

> 혹시 설치 하실때 primary port가 기억이 나지 않으신다면
{ **Installation directory }/IntegrationServer/instances/default/logs로 들어가시면**
server.log 라는 text 파일이 있습니다 해당 파일을 열어서 http 라고 검색해보시면
아래와 같이 두개가 검색이 되실텐데 **primary port,** **diagonostic port**
두개가 검색 되는 것입니다 두개 중 primary port만 위와 같은 화면으로 접속 되니
확인 해보시면 될 것 같습니다.
> 

![Untitled](/assets/img/Untitled%2027.png)

다시 화면으로 돌아가서

Username 과 Password를 입력 해주시면 됩니다 Username은 Administrator이고 패스워드는

설치할 때 설명드렸던 기본 계정 비밀번호 입니다. 저는 manage로 했으니 접속 해보겠습니다.

![Untitled](/assets/img/Untitled%2028.png)

접속이 잘 되셨다면 위와 같은 화면이 나오면 성공하신 겁니다.
integration server 버전에 따라 관리 페이지 UI는 다를 수 있습니다.

## 마무리하며

---

긴 시간동안 잘 따라와주셔서 감사드립니다

다음 포스팅에는 webmethods의 개발 툴인 **Designer**에 대해 포스팅 하려고 합니다
Designer는 Eclipse에 플러그인 형태로 제공되다 보니 Eclipse 및 Designer에 대한 간단한 사용법을
포스팅 해보겠습니다.

해당 포스팅에 틀린 점 및 부연해 주실 내용을 댓글로 달아주시면 감사하겠습니다.