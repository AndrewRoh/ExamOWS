<p align="center">
    <br>
    <img src="img/Logo512pxWhite.png" alt="SabreDartStudios" width="120">
    <h2 align="center">Open World Server (OWS)</h2>
    <h4 align="center"><a href="http://www.sabredartstudios.com/">By SabreDartStudios</a></h4>
</p>
<h1></h1>
<p align="center">
    <img alt="GitHub Workflow Status" src="https://img.shields.io/github/workflow/status/Dartanlla/OWS/Continuous%20Integration?style=flat-square">
    <a href="https://github.com/Dartanlla/OWS/blob/master/LICENSE">
        <img src="https://img.shields.io/github/license/Dartanlla/ows.svg?style=flat-square">
    </a>
    <a href="https://discord.gg/qZ76Cmxcgp">
        <img src="https://img.shields.io/badge/Discord-%237289DA.svg?style=flat-square&logo=discord&logoColor=white" alt="Join Discord">
    </a>
    <img src="https://img.shields.io/badge/unrealengine-%23313131.svg?style=flat-square&logo=unrealengine&logoColor=white">
    <img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=flat-square&logo=docker&logoColor=white">
    <img src="https://img.shields.io/badge/.NET-5C2D91?style=flat-square&logo=.net&logoColor=white">
</p>

OWS(Open World Server)는 UE4에서 대규모 세계를 생성하도록 설계된 서버 인스턴스 관리자입니다. 여러 UE4, UE5 맵을 함께 연결하거나 단일 대형 맵을 여러 영역으로 분할하여 OWS는 세계 인구에 따라 필요에 따라 서버 인스턴스를 가동 및 종료합니다. OWS는 여러 하드웨어 장치 간에 부하를 분산할 수 있습니다. OWS는 인스턴싱 업 및 아웃을 통해 동일한 세계에서 수천 명의 플레이어를 지원할 수 있습니다. 단일 영역을 여러 번 인스턴스화하여 한 영역에서 많은 인구를 지원할 수 있습니다. 맵의 영역은 더 많은 인구를 지원하기 위해 여러 구역으로 분할될 수도 있습니다. 서버 인스턴스 관리 외에도 OWS는 계정, 캐릭터, 능력, 인벤토리 등에 대한 지속성을 처리합니다.

# Projects
- [Benchmarks](src/OWSBenchmarks) - 이 프로젝트를 통해 OWS API에서 성능 테스트를 구성하고 실행할 수 있습니다. 이는 특정 변경 사항의 영향을 비교하는 데 중요합니다.
- [Character Persistence](src/OWSCharacterPersistence) - Character Persistence API는 플레이어 캐릭터 및 모든 관련 데이터를 저장하는 역할을 합니다.
- [Data](src/OWSData) - 데이터 저장소 액세스 코드를 저장하는 공유 프로젝트입니다.
- [External Login Providers](src/OWSExternalLoginProviders) - 이 프로젝트에는 Xsolla, Google, Facebook 등과 같은 외부 로그인 공급자와 통합하기 위한 코드가 포함되어 있습니다.
- [Instance Launcher](src/OWSInstanceLauncher) - 이 프로젝트는 OWS 1의 RPG World Server를 대체하는 Instance Launcher를 구축합니다.
- [Instance Management](src/OWSInstanceManagement) - 이 API는 영역 인스턴스 및 OWS 인스턴스 실행기를 관리합니다.
- [Public API](src/OWSPublicAPI) - 이 API는 등록, 로그인 및 게임 연결과 같은 플레이어 클라이언트에서 직접 오는 모든 API 호출을 처리합니다.
- [Shared](src/OWSShared) - 이 프로젝트에는 다른 여러 프로젝트에 필요한 다양한 기타 코드가 있습니다.
- [Tests](src/OWSTests) - 이 프로젝트는 단위 테스트 및 기능 테스트와 벤치마크 도구(개발)를 제공합니다.

# Contributing
* [Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)
* [Naming Guidelines](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/naming-guidelines)
* [Coding Style](https://github.com/dotnet/corefx/blob/368fdfd86ee3a3bf1bca2a6c339ee590f3d6505d/Documentation/coding-guidelines/coding-style.md)

# Documentation
[Open World Server Documentation](https://www.openworldserver.com/)
