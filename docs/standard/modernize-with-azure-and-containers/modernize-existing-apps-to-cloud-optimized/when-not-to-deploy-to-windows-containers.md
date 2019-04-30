---
title: Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Wann Sie nicht auf Windows-Containern bereitstellen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: c5d8f50c7b9967eba0ec01c9e864a02b6a3b201a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012008"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte

Einige Windows-Technologien werden von Windows-Container nicht unterstützt. In diesen Fällen müssen Sie weiterhin auf Standards-VMs in der Regel mit nur Windows und IIS zu migrieren.

Fälle, in der Windows-Container seit Mai 2018 nicht unterstützt:

- Microsoft Message Queuing (MSMQ) ist derzeit nur in Windows-Containern basierend auf Windows Server-v1803-Version, jedoch nicht in andere Vorgängerversionen verfügbar.

  - [Anforderung UserVoice-forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Diskussionsforum](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Microsoft Distributed Transaction Coordinator (MSDTC) ist in Windows-Containern ist derzeit nicht unterstützt.

  - [GitHub-Problem](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office unterstützt derzeit keine Container.

  - [Anforderung UserVoice-forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- UI-apps (Client-apps mit einer visuellen Benutzeroberfläche) sind nicht unterstützten Szenarien.

- Windows-Infrastrukturrollen (DNS, DHCP, DC, NTP, drucken, Dateiserver IAM usw.) sind nicht unterstützte Szenarien.

Weitere nicht unterstützte Szenarien und Anforderungen von der Community finden Sie in der UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Virtuelle Computer und Container in Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Zurück](deploy-existing-net-apps-as-windows-containers.md)
> [Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
