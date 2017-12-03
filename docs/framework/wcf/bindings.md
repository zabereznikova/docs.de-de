---
title: Windows Communication Foundation-Bindungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36924bdc79a9789a991befb53c0025b7ea1fd601
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="65441-102">Windows Communication Foundation-Bindungen</span><span class="sxs-lookup"><span data-stu-id="65441-102">Windows Communication Foundation Bindings</span></span>
<span data-ttu-id="65441-103">Bindungen bestimmen, wie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienstendpunkt mit anderen Endpunkten kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="65441-103">Bindings specify how a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="65441-104">Eine Bindung muss grundsätzlich erst einmal den zu verwendenden Transportweg festlegen (z. B. HTTP oder TCP).</span><span class="sxs-lookup"><span data-stu-id="65441-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="65441-105">Sie können jedoch auch andere Merkmale wie Sicherheit und Transaktionssupport über Bindungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="65441-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65441-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="65441-106">In This Section</span></span>  
 [<span data-ttu-id="65441-107">WCF-Bindungsübersicht</span><span class="sxs-lookup"><span data-stu-id="65441-107">WCF Bindings Overview</span></span>](../../../docs/framework/wcf/bindings-overview.md)  
 <span data-ttu-id="65441-108">Übersicht über die Aufgaben von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Bindungen, darüber, welche Bindungen das System bereitstellt und wie Sie sie definieren und bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="65441-108">Overview of what [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="65441-109">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="65441-109">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 <span data-ttu-id="65441-110">Eine Liste der Bindungen in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65441-110">A list of bindings included with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="65441-111">Diese Bindungen decken den größten Teil der Sicherheitsanforderungen und Nachrichtenmusteranforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="65441-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="65441-112">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="65441-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="65441-113">Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Bindung enthält wichtige Informationen, mit denen Clients einen Verbindung zu den Dienstendpunkten herstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="65441-113">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="65441-114">Konfigurieren von Bindungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="65441-114">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="65441-115">Durch eine entsprechende Konfiguration können Administratoren und Installationsprogramme die Bindungen für die Dienstendpunkte anpassen.</span><span class="sxs-lookup"><span data-stu-id="65441-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="65441-116">Verweis</span><span class="sxs-lookup"><span data-stu-id="65441-116">Reference</span></span>  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="65441-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="65441-117">Related Sections</span></span>  
 [<span data-ttu-id="65441-118">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="65441-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="65441-119">Bindungen</span><span class="sxs-lookup"><span data-stu-id="65441-119">Bindings</span></span>](../../../docs/framework/wcf/feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="65441-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65441-120">See Also</span></span>  
 [<span data-ttu-id="65441-121">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="65441-121">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
