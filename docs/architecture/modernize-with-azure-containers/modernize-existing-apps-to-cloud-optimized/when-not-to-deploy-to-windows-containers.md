---
title: Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577953"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte

Einige Windows-Technologien werden von Windows-Containern nicht unterstützt. In diesen Fällen müssen Sie immer noch zu Standard-VMs migrieren, normalerweise nur mit Windows und IIS.

Seit Mai 2018 in Windows-Containern nicht unterstützte Fälle:

- Microsoft Message Queuing (MSMQ) ist zurzeit nur in Windows-Containern verfügbar, die auf dem Windows Server-Release v1803 basieren, aber nicht in früheren Versionen.

  - [UserVoice-Anforderungsforum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Diskussionsforum](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Der Microsoft Distributed Transaction Coordinator (MSDTC) wird zurzeit in Windows-Containern nicht unterstützt.

  - [GitHub-Problem](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office unterstützt zurzeit keine Container.

  - [UserVoice-Anforderungsforum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Benutzeroberflächen-Apps (Client-Apps mit einer grafischen Benutzeroberfläche) sind keine unterstützten Szenarios.

- Windows-Infrastrukturrollen (DNS, DHCP, DC, NTP, PRINT, Dateiserver, IAM usw.) sind keine unterstützten Szenarios.

Weitere nicht unterstützte Szenarios und Anforderungen aus der Community finden Sie im UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Virtuelle Computer und Container in Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Zurück](deploy-existing-net-apps-as-windows-containers.md)
> [Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
