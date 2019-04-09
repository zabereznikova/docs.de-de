---
title: Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Wann Sie nicht auf Windows-Containern bereitstellen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 75db31a8f4599e9681c2c4156d93db5416d2ca96
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200739"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="02f4b-103">Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte</span><span class="sxs-lookup"><span data-stu-id="02f4b-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="02f4b-104">Einige Windows-Technologien werden von Windows-Container nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02f4b-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="02f4b-105">In diesen Fällen müssen Sie weiterhin auf Standards-VMs in der Regel mit nur Windows und IIS zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="02f4b-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="02f4b-106">Fälle, in der Windows-Container seit Mai 2018 nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="02f4b-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="02f4b-107">Microsoft Message Queuing (MSMQ) ist derzeit nur in Windows-Containern basierend auf Windows Server-v1803-Version, jedoch nicht in andere Vorgängerversionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="02f4b-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="02f4b-108">Anforderung UserVoice-forum</span><span class="sxs-lookup"><span data-stu-id="02f4b-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="02f4b-109">Diskussionsforum</span><span class="sxs-lookup"><span data-stu-id="02f4b-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="02f4b-110">Microsoft Distributed Transaction Coordinator (MSDTC) ist in Windows-Containern ist derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02f4b-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="02f4b-111">GitHub-Problem</span><span class="sxs-lookup"><span data-stu-id="02f4b-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="02f4b-112">Microsoft Office unterstützt derzeit keine Container.</span><span class="sxs-lookup"><span data-stu-id="02f4b-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="02f4b-113">Anforderung UserVoice-forum</span><span class="sxs-lookup"><span data-stu-id="02f4b-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="02f4b-114">UI-apps (Client-apps mit einer visuellen Benutzeroberfläche) sind nicht unterstützten Szenarien.</span><span class="sxs-lookup"><span data-stu-id="02f4b-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="02f4b-115">Windows-Infrastrukturrollen (DNS, DHCP, DC, NTP, drucken, Dateiserver IAM usw.) sind nicht unterstützte Szenarien.</span><span class="sxs-lookup"><span data-stu-id="02f4b-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="02f4b-116">Weitere nicht unterstützte Szenarien und Anforderungen von der Community finden Sie in der UserVoice-Forum für Windows-Container: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="02f4b-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="02f4b-117">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="02f4b-117">Additional resources</span></span>

-   **<span data-ttu-id="02f4b-118">Virtuelle Computer und Container in Azure</span><span class="sxs-lookup"><span data-stu-id="02f4b-118">Virtual machines and containers in Azure</span></span>**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
><span data-ttu-id="02f4b-119">[Zurück](deploy-existing-net-apps-as-windows-containers.md)
>[Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="02f4b-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>