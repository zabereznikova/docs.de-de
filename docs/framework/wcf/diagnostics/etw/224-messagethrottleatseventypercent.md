---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2f96aea0df629c24eb9d795a4409cae6a9c9aa9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="1d0dd-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="1d0dd-102">224 - MessageThrottleAtSeventyPercent</span></span>
## <a name="properties"></a><span data-ttu-id="1d0dd-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1d0dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d0dd-104">ID</span><span class="sxs-lookup"><span data-stu-id="1d0dd-104">ID</span></span>|<span data-ttu-id="1d0dd-105">224</span><span class="sxs-lookup"><span data-stu-id="1d0dd-105">224</span></span>|  
|<span data-ttu-id="1d0dd-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="1d0dd-106">Keywords</span></span>|<span data-ttu-id="1d0dd-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1d0dd-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1d0dd-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1d0dd-108">Level</span></span>|<span data-ttu-id="1d0dd-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="1d0dd-109">Warning</span></span>|  
|<span data-ttu-id="1d0dd-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1d0dd-110">Channel</span></span>|<span data-ttu-id="1d0dd-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1d0dd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d0dd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d0dd-112">Description</span></span>  
 <span data-ttu-id="1d0dd-113">Wenn eine der Hauptdienstdrosselungen überschritten wurde, wird das `MessageThrottleExceeded`-Ereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="1d0dd-114">Wenn die Aktivitätsauslastung zurückgeht und der aktuelle Wert der Drosselung bei 70 Prozent der aktuellen Grenze liegt, wird dieses Ereignis ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="1d0dd-115">Beachten Sie, dass dieses Ereignis erst ausgegeben wird, nachdem sich die Aktivitätsauslastung abgeschwächt hat.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="1d0dd-116">Wenn sich der aktuelle Wert um die 70-Prozent-Marke bewegt (z. B. 70,69,70,71,70,69), führt nur das erste Erreichen von 70 Prozent zu einem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="1d0dd-117">Nachdem dieses Ereignis ausgegeben wurde, führt das nachfolgende Erreichen der Drosselungsgrenze zu einem `MessageThrottleExceeded`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d0dd-118">Meldung</span><span class="sxs-lookup"><span data-stu-id="1d0dd-118">Message</span></span>  
 <span data-ttu-id="1d0dd-119">Die '%1'-Drosselungsgrenze von '%2' liegt bei 70%%.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d0dd-120">Details</span><span class="sxs-lookup"><span data-stu-id="1d0dd-120">Details</span></span>  
  
|<span data-ttu-id="1d0dd-121">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1d0dd-121">Data Item Name</span></span>|<span data-ttu-id="1d0dd-122">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1d0dd-122">Data Item Type</span></span>|<span data-ttu-id="1d0dd-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d0dd-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d0dd-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="1d0dd-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="1d0dd-125">Der Name der Drosselung, die überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="1d0dd-126">Dies ist entweder `MaxConcurrentCalls`, `MaxConcurrentInstances` oder `MaxConcurrentSessions`.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="1d0dd-127">Limit</span><span class="sxs-lookup"><span data-stu-id="1d0dd-127">Limit</span></span>|`xs:long`|<span data-ttu-id="1d0dd-128">Die momentan konfigurierte Grenze der Drosselung.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="1d0dd-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="1d0dd-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="1d0dd-130">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1d0dd-131">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="1d0dd-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1d0dd-132">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1d0dd-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1d0dd-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1d0dd-134">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d0dd-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
