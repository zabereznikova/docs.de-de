---
title: "Wenn nicht für die Bereitstellung auf Windows-Containern"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Wenn nicht für die Bereitstellung auf Windows-Containern"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb671ec88da7ff1aa5c960c210e0da5e9d753280
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Wenn nicht für die Bereitstellung auf Windows-Containern

Einige Windows-Technologien werden von Windows-Containern nicht unterstützt. In diesen Fällen müssen Sie immer noch auf Standards VMs, in der Regel mit nur Windows und IIS zu migrieren.

Fälle, die nicht in Windows-Container seit Mitte 2017 unterstützt:

-   Microsoft Message Queuing (MSMQ) ist in Windows-Containern ist derzeit nicht unterstützt.

    -   [UserVoice-Anforderung-forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Diskussionsforum](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator (MSDTC) wird im Windows-Containern derzeit nicht unterstützt.

    -   [GitHub-Problem](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office unterstützt derzeit keine Container

    -   [UserVoice-Anforderung-forum](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

Zusätzliche nicht unterstützte Szenarien und Anforderungen aus der Community finden Sie das UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Virtuelle Computer und Container in Azure**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Zurück](deploy-existing-net-apps-as-windows-containers.md)
[Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
