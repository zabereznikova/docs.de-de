---
title: 225 - TraceCorrelationKeys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a8d9120c4173d90d7bf6b1ff2054117f80ac96a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="26e51-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="26e51-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="26e51-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="26e51-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26e51-104">ID</span><span class="sxs-lookup"><span data-stu-id="26e51-104">ID</span></span>|<span data-ttu-id="26e51-105">225</span><span class="sxs-lookup"><span data-stu-id="26e51-105">225</span></span>|  
|<span data-ttu-id="26e51-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="26e51-106">Keywords</span></span>|<span data-ttu-id="26e51-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="26e51-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="26e51-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="26e51-108">Level</span></span>|<span data-ttu-id="26e51-109">Information</span><span class="sxs-lookup"><span data-stu-id="26e51-109">Information</span></span>|  
|<span data-ttu-id="26e51-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="26e51-110">Channel</span></span>|<span data-ttu-id="26e51-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="26e51-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26e51-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26e51-112">Description</span></span>  
 <span data-ttu-id="26e51-113">Dieses Ereignis wird ausgegeben, wenn die inhaltsbasierte Korrelation für einen Workflowdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="26e51-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="26e51-114">Es enthält die Korrelationsschlüssel, die angewendet werden, um eine Nachricht mit einer Instanz zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="26e51-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26e51-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="26e51-115">Message</span></span>  
 <span data-ttu-id="26e51-116">Berechneter Korrelationsschlüssel '%1' mit den Werten '%2' im übergeordneten Bereich '%3'.</span><span class="sxs-lookup"><span data-stu-id="26e51-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26e51-117">Details</span><span class="sxs-lookup"><span data-stu-id="26e51-117">Details</span></span>  
  
|<span data-ttu-id="26e51-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="26e51-118">Data Item Name</span></span>|<span data-ttu-id="26e51-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="26e51-119">Data Item Type</span></span>|<span data-ttu-id="26e51-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26e51-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26e51-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="26e51-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="26e51-122">Der Schlüssel, der aus den Korrelationswerten generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="26e51-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="26e51-123">Werte</span><span class="sxs-lookup"><span data-stu-id="26e51-123">Values</span></span>|`xs:string`|<span data-ttu-id="26e51-124">Die Werte, die verwendet wurden, um den Korrelationsinstanzschlüssel zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="26e51-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="26e51-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="26e51-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="26e51-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="26e51-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="26e51-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="26e51-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="26e51-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="26e51-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="26e51-129">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="26e51-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="26e51-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26e51-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="26e51-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="26e51-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
