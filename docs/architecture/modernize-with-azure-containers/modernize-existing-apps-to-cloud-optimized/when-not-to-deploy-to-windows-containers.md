---
title: Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Keine Bereitstellung in Windows-Containern
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577953"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte

Einige Windows-Technologien werden von Windows-Containern nicht unterstützt. In diesen Fällen müssen Sie immer noch zu Standard-VMS migrieren, normalerweise nur mit Windows und IIS.

Fälle, die in Windows-Containern nicht unterstützt werden, ab Mai 2018:

- Microsoft Message Queuing (MSMQ) ist zurzeit nur in Windows-Containern verfügbar, die auf Windows Server v1803 Release basieren, aber nicht in früheren Versionen.

  - [UserVoice-Anforderungs Forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Diskussionsforum](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Microsoft Distributed Transaction Coordinator (MSDTC) wird derzeit in Windows-Containern nicht unterstützt.

  - [GitHub-Problem](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- In Microsoft Office werden Container derzeit nicht unterstützt.

  - [UserVoice-Anforderungs Forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Benutzeroberflächen-Apps (Client-apps mit einer visuellen Benutzeroberfläche) werden nicht unterstützt.

- Windows-Infrastruktur Rollen (DNS, DHCP, DC, NTP, Print, Dateiserver, IAM usw.) werden nicht unterstützt.

Weitere nicht unterstützte Szenarien und Anforderungen aus der Community finden Sie im UserVoice-Forum für Windows-Container <https://windowsserver.uservoice.com/forums/304624-containers>:.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Virtuelle Computer und Container in Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Zurück](deploy-existing-net-apps-as-windows-containers.md)
> [Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
