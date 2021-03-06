---
# required metadata

title: ATA 구성 변경 - ATA 센터 인증서 | Microsoft Advanced Threat Analytics
description: ATA 센터 서버에서 로컬 컴퓨터 저장소의 인증서를 갱신하거나 바꾸기 위한 2단계 프로세스에 대해 설명합니다. 
keywords:
author: rkarlin
manager: stevenpo
ms.date: 04/28/2016
ms.topic: article
ms.prod: identity-ata
ms.service: advanced-threat-analytics
ms.technology: security
ms.assetid: c8855287-de3b-4cdd-be8f-2128f48a6f27

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: bennyl
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# ATA 구성 변경 - ATA 센터 인증서

>[!div class="step-by-step"]
[« ATA 센터 서버 IP 주소](modifying-ata-config-centerip.md)
[ATA 콘솔 IP 주소 »](modifying-ata-config-consoleip.md)

## ATA 센터 인증서 변경
인증서가 만료되었거나, ATA 센터 서버의 로컬 컴퓨터 저장소에서 새 인증서를 설치한 후 인증서를 갱신 또는 바꾸어야 할 경우 다음 2단계 프로세스를 진행하여 인증서를 바꿉니다.

-   첫 번째 단계 – ATA 센터에서 사용할 인증서를 업데이트합니다. 이때 ATA 센터 서비스는 여전히 원래 인증서에 바인딩되어 있습니다. ATA 게이트웨이는 구성을 동기화하는 경우 상호 인증에 사용할 수 있는 두 가지 잠재적인 인증서를 갖게 됩니다. ATA 게이트웨이는 원래 인증서를 사용하여 연결할 수 있으면 새 인증서 사용을 시도하지 않습니다.

-   두 번째 단계 – 모든 ATA 게이트웨이가 업데이트된 구성과 동기화된 후에는 ATA 센터 서비스가 바인딩된 새 인증서를 활성화할 수 있습니다. 새 인증서를 활성화하면 ATA 센터 서비스가 해당 인증서에 바인딩됩니다. ATA 게이트웨이는 ATA 센터 서비스를 올바르게 상호 인증할 수 없으며 두 번째 인증서를 인증하려고 합니다. ATA 게이트웨이는 ATA 센터 서비스에 연결한 후에 최신 구성을 끌어오고 ATA 센터에 대해 단일 인증서를 갖게 됩니다. (해당 프로세스를 다시 시작하지 않은 경우)

> [!NOTE]
> -   ATA 게이트웨이가 첫 번째 단계 동안 오프라인 상태가 되어 업데이트된 구성을 받지 못하면 ATA 게이트웨이에서 구성 JSON 파일을 수동으로 업데이트해야 합니다.
> -   ATA 게이트웨이에서 신뢰하는 인증서를 사용해야 합니다.
> -   새 인증서를 활성화한 후 새 데이터 게이트웨이 배포해야 하는 경우 ATA 게이트웨이 설치 패키지를 다시 다운로드해야 합니다.

1.  ATA 콘솔을 엽니다.

2.  도구 모음에서 설정 옵션을 선택하고 **구성**을 선택합니다.

    ![ATA 구성 설정 아이콘](media/ATA-config-icon.JPG)

3.  **ATA 센터**를 선택합니다.

4.  **인증서** 아래에서 목록에 있는 인증서 중 하나를 선택합니다.

5.  **저장**을 클릭합니다.

6.  최신 구성과 동기화된 ATA 게이트웨이 수에 대한 알림이 표시됩니다.

7.  모든 ATA 게이트웨이가 동기화된 후 **활성화**를 클릭하여 새 인증서를 활성화합니다.

8.  변경 내용이 활성화된 후 모든 ATA 게이트웨이가 해당 구성을 동기화할 수 있는지 확인합니다.

>[!div class="step-by-step"]
[« ATA 센터 서버 IP 주소](modifying-ata-config-centerip.md)
[ATA 콘솔 IP 주소 »](modifying-ata-config-consoleip.md)

## 참고 항목
- [ATA 콘솔 작업](/advanced-threat-analytics/understand/working-with-ata-console)
- [ATA 설치](install-ata.md)
- [지원이 필요한 경우 포럼을 확인하세요.](https://social.technet.microsoft.com/Forums/security/en-US/home?forum=mata)


<!--HONumber=Apr16_HO2-->


