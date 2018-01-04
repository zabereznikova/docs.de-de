---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 299cc11dc4f6794b65761ad7da71bcf062c318db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="210---messagethrottleexceeded"></a><span data-ttu-id="01e0c-102">210 - MessageThrottleExceeded</span><span class="sxs-lookup"><span data-stu-id="01e0c-102">210 - MessageThrottleExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="01e0c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="01e0c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01e0c-104">Id</span><span class="sxs-lookup"><span data-stu-id="01e0c-104">ID</span></span>|<span data-ttu-id="01e0c-105">210</span><span class="sxs-lookup"><span data-stu-id="01e0c-105">210</span></span>|  
|<span data-ttu-id="01e0c-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="01e0c-106">Keywords</span></span>|<span data-ttu-id="01e0c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="01e0c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="01e0c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="01e0c-108">Level</span></span>|<span data-ttu-id="01e0c-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="01e0c-109">Warning</span></span>|  
|<span data-ttu-id="01e0c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="01e0c-110">Channel</span></span>|<span data-ttu-id="01e0c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="01e0c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01e0c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01e0c-112">Description</span></span>  
 <span data-ttu-id="01e0c-113">Dieses Ereignis wird ausgegeben, wenn eine der drei Hauptdienstdrosselungen überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="01e0c-113">This event is emitted when one of the three main service throttles have been exceeded.</span></span> <span data-ttu-id="01e0c-114">Beachten Sie, dass dieses Ereignis nur ausgegeben wird, wenn die Drosselungsgrenze anfänglich überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="01e0c-114">Note that this event is only emitted when the throttle limit is initially exceeded.</span></span> <span data-ttu-id="01e0c-115">Wenn die Drosselungsgrenze für gleichzeitige Aufrufe z. B. 10 beträgt, führt der elfte gleichzeitige Aufruf zu einem `MessageThrottleExceeded`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="01e0c-115">For example, if the throttle limit for concurrent calls is 10, the 11th concurrent call results in a `MessageThrottleExceeded` event.</span></span> <span data-ttu-id="01e0c-116">Der zwölfte Aufruf führt nicht zu einem weiteren Ereignis.</span><span class="sxs-lookup"><span data-stu-id="01e0c-116">The 12th call does not result in another event.</span></span> <span data-ttu-id="01e0c-117">Um einen unübersichtlichen Ereignistream zu vermeiden, führen Aktivitäten in der Nähe der Grenze nicht zu weiteren Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="01e0c-117">Additionally, to avoid a noisy event stream, activity that hovers around the limit does not result in another event.</span></span> <span data-ttu-id="01e0c-118">Wenn in diesem Beispiel zwei Aufrufe abgeschlossen werden, sind neun gleichzeitige Aufrufe vorhanden.</span><span class="sxs-lookup"><span data-stu-id="01e0c-118">In this example, if a couple of calls complete then there are 9 concurrent calls.</span></span> <span data-ttu-id="01e0c-119">Falls dann zwei weitere Aufrufe eingehen, beträgt der aktuelle Wert wieder 11.</span><span class="sxs-lookup"><span data-stu-id="01e0c-119">If subsequently two more calls come in, the current value is again 11.</span></span> <span data-ttu-id="01e0c-120">Dies führt nicht zu einem weiteren Ereignis.</span><span class="sxs-lookup"><span data-stu-id="01e0c-120">This does not result in another event.</span></span> <span data-ttu-id="01e0c-121">Wenn der aktuelle WErt afu 70 Prozent der Drosselungsgrenze fällt, wird ein anderes Ereignis ausgegeben, das die Verlangsamung der Aktivität angibt.</span><span class="sxs-lookup"><span data-stu-id="01e0c-121">When the current value falls to 70 percent of the throttle limit a different event is emitted that indicates that the activity has slowed.</span></span> <span data-ttu-id="01e0c-122">Darauffolgende Aktivitäten, die die Grenze überschreiten, führen zur Ausgabe eines weiteren `MessageThrottleExceeded`-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="01e0c-122">Future activity that exceeds the limit results in another `MessageThrottleExceeded` event being emitted.</span></span> <span data-ttu-id="01e0c-123">Falls die Anzahl gleichzeitiger Aufrufe in diesem Beispiel auf 7 fällt und dann wieder 11 erreicht, wird ein weiteres `MessageThrottleExceeded`-Ereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="01e0c-123">In this example, if the amount of concurrent calls falls to 7 and then again reaches 11 and another `MessageThrottleExceeded` event is emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01e0c-124">Meldung</span><span class="sxs-lookup"><span data-stu-id="01e0c-124">Message</span></span>  
 <span data-ttu-id="01e0c-125">Die '% 1'-Drosselungsgrenze von '%2' wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="01e0c-125">The '%1' throttle limit of '%2' was hit.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01e0c-126">Details</span><span class="sxs-lookup"><span data-stu-id="01e0c-126">Details</span></span>  
  
|<span data-ttu-id="01e0c-127">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="01e0c-127">Data Item Name</span></span>|<span data-ttu-id="01e0c-128">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="01e0c-128">Data Item Type</span></span>|<span data-ttu-id="01e0c-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01e0c-129">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01e0c-130">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="01e0c-130">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="01e0c-131">Der Name der Drosselung, die überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="01e0c-131">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="01e0c-132">Dies ist entweder `MaxConcurrentCalls`, `MaxConcurrentInstances` oder `MaxConcurrentSessions`.</span><span class="sxs-lookup"><span data-stu-id="01e0c-132">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="01e0c-133">Limit</span><span class="sxs-lookup"><span data-stu-id="01e0c-133">Limit</span></span>|`xs:long`|<span data-ttu-id="01e0c-134">Die momentan konfigurierte Grenze der Drosselung.</span><span class="sxs-lookup"><span data-stu-id="01e0c-134">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="01e0c-135">HostReference</span><span class="sxs-lookup"><span data-stu-id="01e0c-135">HostReference</span></span>|`xs:string`|<span data-ttu-id="01e0c-136">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="01e0c-136">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="01e0c-137">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="01e0c-137">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="01e0c-138">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="01e0c-138">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="01e0c-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="01e0c-139">AppDomain</span></span>|`xs:string`|<span data-ttu-id="01e0c-140">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="01e0c-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
