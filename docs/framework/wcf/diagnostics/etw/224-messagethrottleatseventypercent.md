---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243520"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="93487-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="93487-102">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="93487-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="93487-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93487-104">id</span><span class="sxs-lookup"><span data-stu-id="93487-104">ID</span></span>|<span data-ttu-id="93487-105">224</span><span class="sxs-lookup"><span data-stu-id="93487-105">224</span></span>|  
|<span data-ttu-id="93487-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="93487-106">Keywords</span></span>|<span data-ttu-id="93487-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="93487-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="93487-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="93487-108">Level</span></span>|<span data-ttu-id="93487-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="93487-109">Warning</span></span>|  
|<span data-ttu-id="93487-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="93487-110">Channel</span></span>|<span data-ttu-id="93487-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="93487-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93487-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="93487-112">Description</span></span>  

 <span data-ttu-id="93487-113">Wenn eine der Hauptdienstdrosselungen überschritten wurde, wird das `MessageThrottleExceeded`-Ereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="93487-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="93487-114">Wenn die Aktivitätsauslastung zurückgeht und der aktuelle Wert der Drosselung bei 70 Prozent der aktuellen Grenze liegt, wird dieses Ereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="93487-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="93487-115">Beachten Sie, dass dieses Ereignis erst ausgegeben wird, nachdem sich die Aktivitätsauslastung abgeschwächt hat.</span><span class="sxs-lookup"><span data-stu-id="93487-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="93487-116">Wenn sich der aktuelle Wert um die 70-Prozent-Marke bewegt (z. B. 70,69,70,71,70,69), führt nur das erste Erreichen von 70 Prozent zu einem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="93487-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="93487-117">Nachdem dieses Ereignis ausgegeben wurde, führt das nachfolgende Erreichen der Drosselungsgrenze zu einem `MessageThrottleExceeded`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="93487-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="93487-118">`Message`</span><span class="sxs-lookup"><span data-stu-id="93487-118">Message</span></span>  

 <span data-ttu-id="93487-119">Die '%1'-Drosselungsgrenze von '%2' liegt bei 70%%.</span><span class="sxs-lookup"><span data-stu-id="93487-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="93487-120">Details</span><span class="sxs-lookup"><span data-stu-id="93487-120">Details</span></span>  
  
|<span data-ttu-id="93487-121">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="93487-121">Data Item Name</span></span>|<span data-ttu-id="93487-122">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="93487-122">Data Item Type</span></span>|<span data-ttu-id="93487-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="93487-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="93487-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="93487-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="93487-125">Der Name der Drosselung, die überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="93487-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="93487-126">Dies ist entweder `MaxConcurrentCalls`, `MaxConcurrentInstances` oder `MaxConcurrentSessions`.</span><span class="sxs-lookup"><span data-stu-id="93487-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="93487-127">Begrenzung</span><span class="sxs-lookup"><span data-stu-id="93487-127">Limit</span></span>|`xs:long`|<span data-ttu-id="93487-128">Die momentan konfigurierte Grenze der Drosselung.</span><span class="sxs-lookup"><span data-stu-id="93487-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="93487-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="93487-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="93487-130">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="93487-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="93487-131">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="93487-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="93487-132">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="93487-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="93487-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="93487-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="93487-134">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="93487-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
