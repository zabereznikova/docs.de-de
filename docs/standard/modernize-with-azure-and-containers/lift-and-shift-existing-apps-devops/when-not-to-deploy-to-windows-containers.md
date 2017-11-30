---
title: "Wenn nicht für die Bereitstellung auf Windows-Containern"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Wenn nicht für die Bereitstellung auf Windows-Containern"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="9625b-103">Wenn nicht für die Bereitstellung auf Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="9625b-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="9625b-104">Einige Windows-Technologien werden von Windows-Containern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9625b-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="9625b-105">In diesen Fällen müssen Sie immer noch auf Standards VMs, in der Regel mit nur Windows und IIS zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="9625b-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="9625b-106">Fälle, die nicht in Windows-Container seit Mitte 2017 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9625b-106">Cases not supported in Windows Containers, as of mid-2017:</span></span>

-   <span data-ttu-id="9625b-107">Microsoft Message Queuing (MSMQ) ist in Windows-Containern ist derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9625b-107">Microsoft Message Queuing (MSMQ) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="9625b-108">UserVoice-Anforderung-forum</span><span class="sxs-lookup"><span data-stu-id="9625b-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="9625b-109">Diskussionsforum</span><span class="sxs-lookup"><span data-stu-id="9625b-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="9625b-110">Microsoft Distributed Transaction Coordinator (MSDTC) wird im Windows-Containern derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9625b-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers</span></span>

    -   [<span data-ttu-id="9625b-111">GitHub-Problem</span><span class="sxs-lookup"><span data-stu-id="9625b-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="9625b-112">Microsoft Office unterstützt derzeit keine Container</span><span class="sxs-lookup"><span data-stu-id="9625b-112">Microsoft Office currently does not support containers</span></span>

    -   [<span data-ttu-id="9625b-113">UserVoice-Anforderung-forum</span><span class="sxs-lookup"><span data-stu-id="9625b-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

<span data-ttu-id="9625b-114">Zusätzliche nicht unterstützte Szenarien und Anforderungen aus der Community finden Sie das UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="9625b-114">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9625b-115">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9625b-115">Additional resources</span></span>

-   <span data-ttu-id="9625b-116">**Virtuelle Computer und Container in Azure**</span><span class="sxs-lookup"><span data-stu-id="9625b-116">**Virtual machines and containers in Azure**</span></span>

    [<span data-ttu-id="9625b-117">https://docs.Microsoft.com/Azure/Virtual-Machines/Windows/Containers</span><span class="sxs-lookup"><span data-stu-id="9625b-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="9625b-118">[Zurück](deploy-existing-net-apps-as-windows-containers.md)
[Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="9625b-118">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
