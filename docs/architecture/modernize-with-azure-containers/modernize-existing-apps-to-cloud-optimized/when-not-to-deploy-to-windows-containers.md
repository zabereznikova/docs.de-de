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
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="bfabf-103">Umstände, unter denen keine Bereitstellung in Windows-Containern erfolgen sollte</span><span class="sxs-lookup"><span data-stu-id="bfabf-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="bfabf-104">Einige Windows-Technologien werden von Windows-Containern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bfabf-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="bfabf-105">In diesen Fällen müssen Sie immer noch zu Standard-VMS migrieren, normalerweise nur mit Windows und IIS.</span><span class="sxs-lookup"><span data-stu-id="bfabf-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="bfabf-106">Fälle, die in Windows-Containern nicht unterstützt werden, ab Mai 2018:</span><span class="sxs-lookup"><span data-stu-id="bfabf-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="bfabf-107">Microsoft Message Queuing (MSMQ) ist zurzeit nur in Windows-Containern verfügbar, die auf Windows Server v1803 Release basieren, aber nicht in früheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="bfabf-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="bfabf-108">UserVoice-Anforderungs Forum</span><span class="sxs-lookup"><span data-stu-id="bfabf-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="bfabf-109">Diskussionsforum</span><span class="sxs-lookup"><span data-stu-id="bfabf-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="bfabf-110">Microsoft Distributed Transaction Coordinator (MSDTC) wird derzeit in Windows-Containern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bfabf-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="bfabf-111">GitHub-Problem</span><span class="sxs-lookup"><span data-stu-id="bfabf-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="bfabf-112">In Microsoft Office werden Container derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bfabf-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="bfabf-113">UserVoice-Anforderungs Forum</span><span class="sxs-lookup"><span data-stu-id="bfabf-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="bfabf-114">Benutzeroberflächen-Apps (Client-apps mit einer visuellen Benutzeroberfläche) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bfabf-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="bfabf-115">Windows-Infrastruktur Rollen (DNS, DHCP, DC, NTP, Print, Dateiserver, IAM usw.) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bfabf-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="bfabf-116">Weitere nicht unterstützte Szenarien und Anforderungen aus der Community finden Sie im UserVoice-Forum für Windows-Container <https://windowsserver.uservoice.com/forums/304624-containers>:.</span><span class="sxs-lookup"><span data-stu-id="bfabf-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="bfabf-117">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="bfabf-117">Additional resources</span></span>

- <span data-ttu-id="bfabf-118">**Virtuelle Computer und Container in Azure**</span><span class="sxs-lookup"><span data-stu-id="bfabf-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="bfabf-119">[Zurück](deploy-existing-net-apps-as-windows-containers.md)
> [Weiter](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="bfabf-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
