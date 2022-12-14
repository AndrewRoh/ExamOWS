---
layout: default
title: Getting Started
nav_order: 1
has_children: true
---

# Getting Started
Here is a brief overview of OWS 2.

## Why OWS 2?
* OWS 2의 주요 목표는 확장성을 높이고 온라인 멀티플레이어 게임의 동시 플레이어 수를 높이는 것입니다. OWS 2의 목표는 100,000명 이상의 동시 플레이어를 확장하는 것입니다.
* OWS 1은 특정 기술 지식이 없는 개발자가 로컬 개발 환경에 설치하기 어려웠습니다. OWS 2 및 Docker를 사용하면 로컬 개발 환경에서 빠르고 쉽게 설정할 수 있습니다. OWS 2를 로컬에서 실행하면 필요에 맞게 API를 사용자 지정할 수 있습니다.
* OWS 1에는 Windows 및 Windows 서버가 필요했습니다. OWS 2는 기본적으로 Windows , Linux 및 MacOS 에서 실행됩니다 .

## What technologies / architecture does OWS 2 use?
* OWS 웹 API는 .NET 6 (이전의 .NET Core)을 사용하여 C# 으로 개발되었습니다.
* 기본 스토리지 기술은 [Microsoft SQL Server (MSSQL)](mssql) 입니다.
  * 각 리포지토리는 자체 스토리지 기술을 사용할 수 있습니다.
  * 각 리포지토리 인터페이스를 구현하여 [스토리지 기술](setup-database)을 쉽게 추가할 수 있습니다.
* 마이크로서비스를 통해 OWS는 더 쉽게 확장할 수 있습니다.
* 의존성 주입
  * 다양한 구현을 쉽게 플러그인하여 다양한 서비스 및 기술 지원
* [Docker](docker-setup) 로컬 개발 PC에서 클릭 한 번으로 배포할 수 있게 하였습니다.
  * Docker는 컨테이너에서 모든 OWS 서버를 실행합니다.
  * OWS는 Docker를 사용하거나 사용하지 않고 실행할 수 있습니다.
* [Unreal Engine](https://www.unrealengine.com/)
  * OWS 2는 언리얼 엔진의 강력한 서버 아키텍처를 기반으로 사용하여 게임 세계를 채우는 데 필요할 때 동적으로 서버를 가동합니다.

## OWS Network Diagram
![OWS Network Diagram](images/network-diagram.png){: .mt-3}

## Zones & Shards
![Zones & Shards](images/zones.png){: .mt-3}
* 영역은 단일 Unreal Engine 서버가 제어하는 Unreal Engine 맵 또는 Unreal Engine 맵의 영역을 나타냅니다.
* Unreal Engine 맵은 여러 영역으로 분할될 수 있으며 영역에는 여러 샤드가 있을 수 있습니다.
* 세계를 구역으로 분할한 다음 해당 구역을 샤딩하면 게임에 필요한 동시 플레이어 수를 달성할 수 있습니다.
* 다른 영역 및 영역의 샤드에 있는 플레이어는 동일한 영역 또는 샤드에 있는 플레이어만 보거나 상호 작용할 수 있습니다.

### Zone servers & zone server instances
* 영역 서버는 영역 서버 인스턴스를 실행하도록 지정된 하드웨어 장치(서버)입니다.
* 하나 이상의 Zone Server를 OWS에 등록할 수 있습니다.
* 영역 서버 인스턴스는 Unreal Engine 서버 인스턴스입니다.
* 영역 서버는 하나 이상의 영역 서버 인스턴스를 실행할 수 있습니다.
* 영역 서버 인스턴스는 Unreal Engine 맵 또는 Unreal Engine 맵의 섹션을 나타낼 수 있습니다.
* 해당 영역에서 더 많은 플레이어를 허용하기 위해 영역(샤드)당 둘 이상의 영역 서버 인스턴스를 실행할 수 있습니다.
* 영역 서버 인스턴스는 Soft Player Cap 및 Hard Player Cap으로 구성할 수 있습니다. Soft Player Cap이 충족되면 새로운 파편이 회전합니다.

[Next: Docker Setup](docker-setup){: .btn .btn-outline }
