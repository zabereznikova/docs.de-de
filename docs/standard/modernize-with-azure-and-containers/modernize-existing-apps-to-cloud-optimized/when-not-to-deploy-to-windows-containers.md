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
ms.locfileid: "33957960"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="4545f-103">Wenn nicht für die Bereitstellung auf Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="4545f-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="4545f-104">Einige Windows-Technologien werden von Windows-Containern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4545f-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="4545f-105">In diesen Fällen müssen Sie immer noch auf Standards VMs, in der Regel mit nur Windows und IIS zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="4545f-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="4545f-106">Fälle, die nicht in Windows-Containern ab Mai 2018 unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4545f-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="4545f-107">Microsoft Message Queuing (MSMQ) ist zurzeit nur in Windows-Container auf Grundlage der Version von Windows Server v1803, jedoch nicht in andere Vorgängerversionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4545f-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="4545f-108">UserVoice-Anforderung-forum</span><span class="sxs-lookup"><span data-stu-id="4545f-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="4545f-109">Diskussionsforum</span><span class="sxs-lookup"><span data-stu-id="4545f-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="4545f-110">Microsoft Distributed Transaction Coordinator (MSDTC) wird im Windows-Containern derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4545f-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="4545f-111">GitHub-Problem</span><span class="sxs-lookup"><span data-stu-id="4545f-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="4545f-112">Microsoft Office unterstützt derzeit keine Container.</span><span class="sxs-lookup"><span data-stu-id="4545f-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="4545f-113">UserVoice-Anforderung-forum</span><span class="sxs-lookup"><span data-stu-id="4545f-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="4545f-114">UI-apps (Client-apps mit visual-Benutzeroberfläche) sind nicht unterstützte Szenarien.</span><span class="sxs-lookup"><span data-stu-id="4545f-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="4545f-115">Windows-Infrastruktur-Rollen (DNS, DHCP, DC, NTP, drucken, Dateiserver und IAM usw.) sind nicht unterstützte Szenarien.</span><span class="sxs-lookup"><span data-stu-id="4545f-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="4545f-116">Zusätzliche nicht unterstützte Szenarien und Anforderungen aus der Community finden Sie das UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="4545f-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4545f-117">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4545f-117">Additional resources</span></span>

-   <span data-ttu-id="4545f-118">**Virtuelle Computer und Container in Azure**</span><span class="sxs-lookup"><span data-stu-id="4545f-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="4545f-119">[Zurück](deploy-existing-net-apps-as-windows-containers.md)
[Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="4545f-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
