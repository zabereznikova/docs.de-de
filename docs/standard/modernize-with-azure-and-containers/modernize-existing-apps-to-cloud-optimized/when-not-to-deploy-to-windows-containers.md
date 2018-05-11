---
title: Wenn nicht für die Bereitstellung auf Windows-Containern
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Wenn nicht für die Bereitstellung auf Windows-Containern
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 819f32955ff019414bef8820d17d272eddc11bf8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Wenn nicht für die Bereitstellung auf Windows-Containern

Einige Windows-Technologien werden von Windows-Containern nicht unterstützt. In diesen Fällen müssen Sie immer noch auf Standards VMs, in der Regel mit nur Windows und IIS zu migrieren.

Fälle, die nicht in Windows-Containern ab Mai 2018 unterstützt: 

-   Microsoft Message Queuing (MSMQ) ist zurzeit nur in Windows-Container auf Grundlage der Version von Windows Server v1803, jedoch nicht in andere Vorgängerversionen verfügbar. 

    -   [UserVoice-Anforderung-forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Diskussionsforum](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator (MSDTC) wird im Windows-Containern derzeit nicht unterstützt.

    -   [GitHub-Problem](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office unterstützt derzeit keine Container.

    -   [UserVoice-Anforderung-forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   UI-apps (Client-apps mit visual-Benutzeroberfläche) sind nicht unterstützte Szenarien.

-   Windows-Infrastruktur-Rollen (DNS, DHCP, DC, NTP, drucken, Dateiserver und IAM usw.) sind nicht unterstützte Szenarien.


Zusätzliche nicht unterstützte Szenarien und Anforderungen aus der Community finden Sie das UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Virtuelle Computer und Container in Azure**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Zurück](deploy-existing-net-apps-as-windows-containers.md)
[Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
