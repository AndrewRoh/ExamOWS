---
layout: default
title: MSSQL
parent: Database Setup
grand_parent: Getting Started
nav_order: 1
---

# MSSQL

[MSSQL](https://www.microsoft.com/de-de/sql-server/sql-server-2019)은 Microsoft에서 게시한 데이터베이스 소프트웨어 제품군입니다. 여기에는 데이터를 테이블, 열 및 행에 저장하는 관계형 데이터베이스 엔진이 포함됩니다.

## Update database version

1. SQL Server Management Studio 또는 Azure Data Studio를 열고 다음 자격 증명을 사용하여 localhost에 연결합니다.

    <dl>
        <dt>Username</dt>
        <dd>sa</dd>
        <dt>Password</dt>
        <dd>yourStrong(!)Password</dd>
    </dl>

2. Open World Server 데이터베이스에 대해 다음 SQL 문을 실행합니다.
   
   ```sql
   SELECT * FROM OWSVersion
   ```

3. **OWSDBVersion** 결과 값과 SQL 업데이트 스크립트와 비교하여 `Databases\MSSQL\UpdateScriptsFolder` 데이터베이스에서 실행할 스크립트를 확인합니다.
   
4. 업데이트 스크립트 파일명은 **From[SomeVersion]To[SomeVersion]** 버전 정보로 되어 있습니다. **OWSDBVersion** 값과 **From[SomeVersion]** 을 비교하여 순서대로 실행하여 주십시오. 스크립트를 실행하려면 파일을 열고 내용을 복사한 다음 2단계에서 했던 것처럼 Open World Server 데이터베이스에 대해 SQL 문으로 실행합니다

## Create API Key

1. SQL Server Management Studio 또는 Azure Data Studio를 열고 다음 자격 증명을 사용하여 localhost에 연결합니다.

    <dl>
        <dt>Username</dt>
        <dd>sa</dd>
        <dt>Password</dt>
        <dd>yourStrong(!)Password</dd>
    </dl>

2. Open World Server 데이터베이스에 대해 다음 SQL 문을 실행합니다. 
   (선택 사항): 특정 GUID는 암호 다음에 '00000000-0000-0000-0000-000000000000' 형식으로 선택적 최종 매개 변수로 입력할 수 있습니다.

   ```sql
   EXEC [dbo].[AddNewCustomer] 'CustomerName', 'FirstName', 'LastName', 'Email', 'Password'
   ```
   
   다음 값을 교체해야 합니다.

    <dl>
        <dt>CustomerName</dt>
        <dd>고객의 닉네임 또는 프로필 이름입니다.</dd>
        <dt>FirstName</dt>
        <dd>고객의 이름입니다.</dd>
        <dt>LastName</dt>
        <dd>고객의 성입니다.</dd>
        <dt>Email</dt>
        <dd>고객의 메일 주소를 입력합니다.</dd>
        <dt>Password</dt>
        <dd>안전한 비밀번호를 입력하세요.</dd>
    </dl>
    
3. Open World Server 데이터베이스에 대해 다음 SQL 문을 실행하여 **API key** 를 가져옵니다 . 나중을 위해 키를 저장하십시오.
   
   ```sql
   SELECT TOP 1 CustomerGUID FROM Customers
   ```

[Next: OWS Starter Project](starter-project){: .btn .btn-outline }
