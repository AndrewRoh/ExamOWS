---
layout: default
title: Docker Setup
parent: Getting Started
nav_order: 1
---

# Docker Setup

## Requirements  
* OWS 다운로드 또는 복제
* 다운로드 및 설치 [Visual Studio 2022 Community](https://visualstudio.microsoft.com/downloads/)
  * ASP.NET 및 웹 개발 워크로드가 필요합니다.
* Windows/macOS/Linux [Docker Desktop](https://www.docker.com/products/docker-desktop) 다운로드 및 설치
* [.Net 6.0 SDK]([another-page](https://dotnet.microsoft.com/download/dotnet/6.0))
<br />
<br />

<details open markdown="block">
  <summary class="fs-6 mb-3">
    Windows
  </summary>

1. 다운로드 및 설치 [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop)
2. Visual Studio 2022 Community에서 OWS 프로젝트를 엽니다. [ASP.NET and Web Development workload](../troubleshooting/visual-studio#installing-workloads) 가 필요합니다.
3. Docker Compose 시작 프로젝트를 선택하고 Docker Compose 실행을 선택합니다. ![Launch Docker Compose](images/docker-compose-windows.png){: .mt-3}
4. <span class="label" style="margin-left: -3px">선택</span>  
   Visual Studio 디버거 없이 Docker Compose 실행, OWS 루트 디렉터리에서 다음 명령 프롬프트를 입력합니다.

   ```bash
   docker-compose -f docker-compose.yml -f docker-compose.override.windows.yml -f docker-compose-additional.yml up -d 
   ```

   새로운 빌드의 경우 다음 명령을 사용하십시오.
   
   ```bash
   docker-compose -f docker-compose.yml -f docker-compose.override.windows.yml -f docker-compose-additional.yml up -d --build --force-recreate 
   ```
</details>

<details markdown="block">
  <summary class="fs-6 mb-3">
    macOS
  </summary>

1. Download and install [Docker Desktop for Mac](https://docs.docker.com/desktop/install/mac-install/)
2. Open OWS Project in [Visual Studio For Mac](https://visualstudio.microsoft.com/de/vs/mac/). The [ASP.NET and Web Development workload](../troubleshooting/visual-studio#installing-workloads) is required.
3. Run the following command in a terminal to install the Development Certificates
   
   ```bash
   dotnet dev-certs https --trust
   ```

4. Select Docker Compose startup project and Launch Docker Compose. ![Launch Docker Compose](images/docker-compose-mac.png){: .mt-3}
5. <span class="label" style="margin-left: -3px">Optional</span>  
    Running Docker Compose without Visual Studio Debugger, Run the following command in an terminal from the OWS root directory.

   ```bash
   docker-compose -f docker-compose.yml -f docker-compose.override.osx.yml -f docker-compose-additional.yml up -d 
   ```

   For a fresh build use the following command
   
   ```bash
   docker-compose -f docker-compose.yml -f docker-compose.override.osx.yml -f docker-compose-additional.yml up -d --build --force-recreate 
   ```
</details>

<details markdown="block">
  <summary class="fs-6 mb-3">
    Linux
  </summary>

1. Download and install [Docker Desktop for Linux](https://docs.docker.com/desktop/install/linux-install/)
2. Close all web browsers
3. Download and Run [dotnet-dev-certificate-linux](https://github.com/CodewareGames/dotnet-dev-certificate-linux) to install Development HTTPS Certificate.
4. Run the following command in an terminal from the OWS src directory.

   ```bash
   sudo docker-compose -f docker-compose.yml -f docker-compose.override.linux.yml -f docker-compose-additional.yml up -d 
   ```

   For a fresh build use the following command

   ```bash
   sudo docker-compose -f docker-compose.yml -f docker-compose.override.linux.yml -f docker-compose-additional.yml up -d --build --force-recreate 
   ```
</details>

[Next: Database setup](setup-database){: .btn .btn-outline }
