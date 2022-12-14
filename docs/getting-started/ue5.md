---
layout: default
title: Unreal Engine 5.1.0
parent: OWS Starter Project
grand_parent: Getting Started
nav_order: 1
---

# OWS Starter Project for Unreal Engine 5.1.0
Unreal Engine 5.0.3용 OWS 스타터 프로젝트를 설정하려면 이 지침을 따르십시오. 이 프로젝트를 설정하려면 먼저 [Docker Setup](docker-setup) and [Database setup](setup-database) 섹션을 완료해야 합니다.

## Download the project

Open World Starter 프로젝트를 다운로드하려면 아래 버튼을 클릭하십시오.

[Download OpenWorldStarterDockerUE5.zip - 20221119 Release - UE 5.1.0](https://drive.google.com/file/d/1oE5F0SfRAOdYBVlqMPDv26CDCkcDsWZ-/view?usp=share_link){: .btn .btn-blue .mr-4}

## Initial setup

1. Visual Studio 2022를 사용 하여 [OWS GitHub project](https://github.com/Dartanlla/OWS) 열고 Docker Compose 버튼을 클릭합니다(아직 실행 중이 아닌 경우). 자세한 설명은 [Docker Setup](docker-setup) 섹션을 확인 하십시오. -> 서버 실행 여부 확인 Docker를 확인 하여도 됩니다.
   
2. Unreal Projects 폴더 또는 PC의 다른 위치에 OpenWorldStarterPlugin.zip 압축을 풉니다.
   
3. `/OWSInstanceLauncher/appsettings.json` 메모장에서 파일을 엽니다.
   
4. **PathToDedicatedServer** 값이 최신 버전의 **UnrealEditor.exe** 를 가리키는 지 확인하십시오.
   
5. **OpenWorldStarter.uproject** 에 대한 경로를 포함 하도록 **PathToUProject** 값을 수정합니다. 경로에는 uproject 파일과 파일 확장자도 포함되어야 합니다.

6. [Database setup instructions](setup-database) 에서 생성한 **OWSAPIKey** 값을 입력합니다.

7. `appsettings.json` 파일 저장

8. 다른 사람이 참가할 수 있는 멀티플레이어 게임을 호스팅하려면 라우터 구성을 열고 포트 7777~7787에 대한 UDP를 PC로 전달합니다(최대 10개의 맵 지원).

9. 다른 사람이 참가할 수 있는 멀티플레이어 게임을 호스팅하려면 Windows 방화벽(및 가지고 있는 다른 방화벽 소프트웨어)을 열고 포트 7777~7787에 들어오는 TCP 및 UDP를 허용하는 포트 규칙을 추가합니다.

10. `Config/DefaultGame.ini` 을 열고 APIKey (**OWSAPICustomerKey=""**) 를 **OWSAPIKey** 6단계에서 사용한 것으로 바꿉니다. APIKey의 시작과 끝에 큰따옴표를 유지해야 합니다.

11. **OWSInstanceLauncher** 폴더 에 대한 명령 프롬프트를 엽니다. `dotnet owsinstancelauncher.dll` 명령어 입력 후 Enter 키를 누릅니다. 표시되는 모든 보안 경고에 동의 합니다.

12. OWS Instance Launcher가 작동 중이면 `Attempting to Register OWS Instance Launcher with RabbitMQ ServerSpinUp Queue...` 노란색으로 표시된 다음 `Registered OWS Instance Launcher with RabbitMQ ServerSpinUp Queue Success!` 녹색으로 표시됩니다.

13. 에러가 발생하면 `Unable to configure HTTPS endpoint. No server certificate was specified, and the default developer certificate could not be found or is out of date.`, 명령 프롬프트에서 다음 명령을 실행하고 Enter 키를 누릅니다 `dotnet dev-certs https --trust`. 이제 다시한번 명령문 `dotnet owsinstancelauncher.dll` 실행합니다.

14. **OpenWorldStarter.uproject** 를 마우스 오른쪽 버튼으로 클릭합니다 `Generate Visual Studio project files` 메뉴를 실행합니다..

15. Visual Studio 2022를 사용 하여 **OpenWorldStarter.sln** 파일을 엽니다.  Open World Starter를 기본 시작 프로젝트로 설정합니다. 구성이 **Development Editor** 설정되어 있는지 확인하십시오. 그런 다음 재생 버튼을 누릅니다.

16. 언리얼 엔진에서 프로젝트가 열리면 `ThirdPersonBP/Maps` 폴더를 열고 **Login** 맵을 엽니다. Unreal Engine의 재생 버튼이 **Play as Standalone** 으로 설정되어 있는지 확인합니다 . 언리얼 엔진에서 재생 버튼을 누릅니다.

17. 로그인 화면에서, **Create New User** 를 클릭합니다. 새로 만든 사용자 이름과 암호를 사용하여 로그인하십시오.

18. **Create Character** 버튼을 클릭하여  새로운 캐릭터를 생성합니다.

19. ISP가 자동 루프백을 지원하지 않고 언리얼 엔진 서버가 게임 클라이언트와 동일한 디바이스에서 실행 중인 경우 SQL Server Management Studio(SSMS)를 사용하여 SQL 데이터베이스에 들어가 IsInternalNetworkTestUser를 1로 설정해야 합니다. 연결하려는 캐릭터의 캐릭터 테이블입니다. 당신의 **IP**를 `127.0.0.1` 로 바꾸면 게임 클라이언트와 동일한 장치에서 UE5 서버에 연결할 수 있습니다. 이 설정이 없으면 연결할 수 없으며 로그인 화면으로 돌아갑니다.

20. **Select Character** 버튼을 클릭합니다. 용 서버를 부팅해야 하므로 최초 부팅 시 약 15초가 소요됩니다. Map2(연결된 지도)로 실행하는 것도 처음 부팅할 때 15초가 걸립니다. 설치 및 실행 후 1~2초밖에 걸리지 않습니다.

21. 영역 서버 및 OWS 인스턴스 시작 관리자를 종료하려면 OWS 인스턴스 시작 관리자 콘솔 창으로 활성화하고 **Ctrl-C**를 누릅니다.
