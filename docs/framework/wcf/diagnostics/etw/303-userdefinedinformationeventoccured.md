---
title: 303 - UserDefinedInformationEventOccured
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bd4d94d457793eb036f037cc6dc22bff6d26ee2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="e331d-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="e331d-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="e331d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e331d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e331d-104">Id</span><span class="sxs-lookup"><span data-stu-id="e331d-104">ID</span></span>|<span data-ttu-id="e331d-105">303</span><span class="sxs-lookup"><span data-stu-id="e331d-105">303</span></span>|  
|<span data-ttu-id="e331d-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="e331d-106">Keywords</span></span>|<span data-ttu-id="e331d-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="e331d-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="e331d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e331d-108">Level</span></span>|<span data-ttu-id="e331d-109">Information</span><span class="sxs-lookup"><span data-stu-id="e331d-109">Information</span></span>|  
|<span data-ttu-id="e331d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e331d-110">Channel</span></span>|<span data-ttu-id="e331d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e331d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e331d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e331d-112">Description</span></span>  
 <span data-ttu-id="e331d-113">Dieses Ereignis wird vom Benutzercode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="e331d-113">This event is emitted from user code.</span></span> <span data-ttu-id="e331d-114">Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefiniertes Informationsereignis im Dienst auftritt.</span><span class="sxs-lookup"><span data-stu-id="e331d-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="e331d-115">Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="e331d-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="e331d-116">Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.</span><span class="sxs-lookup"><span data-stu-id="e331d-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e331d-117">Meldung</span><span class="sxs-lookup"><span data-stu-id="e331d-117">Message</span></span>  
 <span data-ttu-id="e331d-118">Name:'%1', Verweis:'%2', Nutzlast:%3</span><span class="sxs-lookup"><span data-stu-id="e331d-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="e331d-119">Details</span><span class="sxs-lookup"><span data-stu-id="e331d-119">Details</span></span>  
  
|<span data-ttu-id="e331d-120">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e331d-120">Data Item Name</span></span>|<span data-ttu-id="e331d-121">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e331d-121">Data Item Type</span></span>|<span data-ttu-id="e331d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e331d-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e331d-123">name</span><span class="sxs-lookup"><span data-stu-id="e331d-123">Name</span></span>|`xs:string`|<span data-ttu-id="e331d-124">Der benutzerdefinierte Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e331d-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="e331d-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="e331d-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="e331d-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="e331d-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e331d-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="e331d-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e331d-128">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e331d-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e331d-129">Payload</span><span class="sxs-lookup"><span data-stu-id="e331d-129">Payload</span></span>|`xs:string`|<span data-ttu-id="e331d-130">Die benutzerdefinierte Nutzlast des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e331d-130">The user-defined payload of the event.</span></span>|
