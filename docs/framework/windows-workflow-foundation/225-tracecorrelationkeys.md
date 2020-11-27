---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294494"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="e2aff-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="e2aff-102">225 - TraceCorrelationKeys</span></span>

## <a name="properties"></a><span data-ttu-id="e2aff-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e2aff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2aff-104">id</span><span class="sxs-lookup"><span data-stu-id="e2aff-104">ID</span></span>|<span data-ttu-id="e2aff-105">225</span><span class="sxs-lookup"><span data-stu-id="e2aff-105">225</span></span>|  
|<span data-ttu-id="e2aff-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="e2aff-106">Keywords</span></span>|<span data-ttu-id="e2aff-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2aff-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e2aff-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e2aff-108">Level</span></span>|<span data-ttu-id="e2aff-109">Information</span><span class="sxs-lookup"><span data-stu-id="e2aff-109">Information</span></span>|  
|<span data-ttu-id="e2aff-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e2aff-110">Channel</span></span>|<span data-ttu-id="e2aff-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e2aff-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e2aff-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e2aff-112">Description</span></span>  

 <span data-ttu-id="e2aff-113">Dieses Ereignis wird ausgegeben, wenn die inhaltsbasierte Korrelation für einen Workflowdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e2aff-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="e2aff-114">Es enthält die Korrelationsschlüssel, die angewendet werden, um eine Nachricht mit einer Instanz zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="e2aff-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e2aff-115">`Message`</span><span class="sxs-lookup"><span data-stu-id="e2aff-115">Message</span></span>  

 <span data-ttu-id="e2aff-116">Berechneter Korrelationsschlüssel '%1' mit den Werten '%2' im übergeordneten Bereich '%3'.</span><span class="sxs-lookup"><span data-stu-id="e2aff-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e2aff-117">Details</span><span class="sxs-lookup"><span data-stu-id="e2aff-117">Details</span></span>  
  
|<span data-ttu-id="e2aff-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e2aff-118">Data Item Name</span></span>|<span data-ttu-id="e2aff-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e2aff-119">Data Item Type</span></span>|<span data-ttu-id="e2aff-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e2aff-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e2aff-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="e2aff-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="e2aff-122">Der Schlüssel, der aus den Korrelationswerten generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2aff-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="e2aff-123">Werte</span><span class="sxs-lookup"><span data-stu-id="e2aff-123">Values</span></span>|`xs:string`|<span data-ttu-id="e2aff-124">Die Werte, die verwendet wurden, um den Korrelationsinstanzschlüssel zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="e2aff-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="e2aff-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="e2aff-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="e2aff-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="e2aff-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="e2aff-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="e2aff-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e2aff-128">Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert.</span><span class="sxs-lookup"><span data-stu-id="e2aff-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e2aff-129">Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e2aff-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e2aff-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e2aff-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e2aff-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e2aff-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
