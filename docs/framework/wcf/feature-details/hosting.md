---
title: Hosting2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0820c7e5-0b50-4cde-80e7-74e346513002
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f25f0c9e773bbadd992284adf6c79d77aaa2441c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hosting"></a><span data-ttu-id="5eb5b-102">Hosting</span><span class="sxs-lookup"><span data-stu-id="5eb5b-102">Hosting</span></span>
<span data-ttu-id="5eb5b-103">In den Themen dieses Abschnitts wird das Diensthosting beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-103">The topics in the section describe service hosting.</span></span> <span data-ttu-id="5eb5b-104">Ein Dienst kann von Internet Information Services (IIS), Windows Process Activation Service (WAS), Windows Server AppFabric, einem Windows-Dienst oder von einer verwalteten Anwendung gehostet werden: Diese Option wird häufig als bezeichnet *Self-hosting*.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-104">A service can be hosted by Internet Information Services (IIS), Windows Process Activation Service (WAS), Windows Server AppFabric, a Windows service, or by a managed application—this option is often referred to as *self hosting*.</span></span>  
  
 <span data-ttu-id="5eb5b-105">Sie müssen unbedingt beachten, dass die Sicherheit gefährdet wird, wenn ein Dienst oder eine Erweiterung auf einem nicht vertrauenswürdigen Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-105">It is important to note that running a service or any extension from an untrusted host compromises security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5eb5b-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5eb5b-106">In This Section</span></span>  
 [<span data-ttu-id="5eb5b-107">Hosten in IIS (Internetinformationsdienste)</span><span class="sxs-lookup"><span data-stu-id="5eb5b-107">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 <span data-ttu-id="5eb5b-108">Beschreibt, wie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Dienst in Internetinformationsdienste (IIS) gehostet wird oder [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496).</span><span class="sxs-lookup"><span data-stu-id="5eb5b-108">Describes how a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is hosted in Internet Information Services or [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496).</span></span>  
  
 [<span data-ttu-id="5eb5b-109">Hosting in Windows Process Activation Service (Hosten im Windows-Prozessaktivierungsdienst)</span><span class="sxs-lookup"><span data-stu-id="5eb5b-109">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 <span data-ttu-id="5eb5b-110">Beschreibt, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst vom Windows-Prozessaktivierungsdienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-110">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by Windows Process Activation Service.</span></span>  
  
 [<span data-ttu-id="5eb5b-111">Hosten in einer Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="5eb5b-111">Hosting in a Windows Service Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-windows-service-application.md)  
 <span data-ttu-id="5eb5b-112">Beschreibt, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst von einem Windows-Dienst gehostet wird</span><span class="sxs-lookup"><span data-stu-id="5eb5b-112">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by a Windows service.</span></span>  
  
 [<span data-ttu-id="5eb5b-113">Hosten in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="5eb5b-113">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 <span data-ttu-id="5eb5b-114">Beschreibt, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst in einer verwalteten Anwendung gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-114">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted in a managed application.</span></span>  
  
 [<span data-ttu-id="5eb5b-115">Konfigurationsbasierte Aktivierung unter IIS und WAS</span><span class="sxs-lookup"><span data-stu-id="5eb5b-115">Configuration-Based Activation in IIS and WAS</span></span>](../../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 <span data-ttu-id="5eb5b-116">Beschreibt, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst unter IIS oder WAS ohne Verwendung einer SVC-Datei gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-116">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted under IIS or WAS without using a .svc file.</span></span>  
  
 [<span data-ttu-id="5eb5b-117">Unterstützen mehrerer IIS-Sitebindungen</span><span class="sxs-lookup"><span data-stu-id="5eb5b-117">Supporting Multiple IIS Site Bindings</span></span>](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md)  
 <span data-ttu-id="5eb5b-118">Beschreibt, wie Sie mehrere Basisadressen für einen Dienst angeben, indem Sie auf einer Website das gleiche URI-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="5eb5b-118">Describes how to specify multiple base addresses for a service using the same URI scheme on a single Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb5b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5eb5b-119">See Also</span></span>  
 [<span data-ttu-id="5eb5b-120">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="5eb5b-120">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="5eb5b-121">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="5eb5b-121">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
