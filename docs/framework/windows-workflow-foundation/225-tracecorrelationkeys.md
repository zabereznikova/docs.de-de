---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755661"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="b52ae-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="b52ae-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="b52ae-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b52ae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b52ae-104">ID</span><span class="sxs-lookup"><span data-stu-id="b52ae-104">ID</span></span>|<span data-ttu-id="b52ae-105">225</span><span class="sxs-lookup"><span data-stu-id="b52ae-105">225</span></span>|  
|<span data-ttu-id="b52ae-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b52ae-106">Keywords</span></span>|<span data-ttu-id="b52ae-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b52ae-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b52ae-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b52ae-108">Level</span></span>|<span data-ttu-id="b52ae-109">Information</span><span class="sxs-lookup"><span data-stu-id="b52ae-109">Information</span></span>|  
|<span data-ttu-id="b52ae-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b52ae-110">Channel</span></span>|<span data-ttu-id="b52ae-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b52ae-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b52ae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b52ae-112">Description</span></span>  
 <span data-ttu-id="b52ae-113">Dieses Ereignis wird ausgegeben, wenn die inhaltsbasierte Korrelation für einen Workflowdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b52ae-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="b52ae-114">Es enthält die Korrelationsschlüssel, die angewendet werden, um eine Nachricht mit einer Instanz zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="b52ae-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b52ae-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="b52ae-115">Message</span></span>  
 <span data-ttu-id="b52ae-116">Berechneter Korrelationsschlüssel '%1' mit den Werten '%2' im übergeordneten Bereich '%3'.</span><span class="sxs-lookup"><span data-stu-id="b52ae-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b52ae-117">Details</span><span class="sxs-lookup"><span data-stu-id="b52ae-117">Details</span></span>  
  
|<span data-ttu-id="b52ae-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b52ae-118">Data Item Name</span></span>|<span data-ttu-id="b52ae-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b52ae-119">Data Item Type</span></span>|<span data-ttu-id="b52ae-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b52ae-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b52ae-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="b52ae-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="b52ae-122">Der Schlüssel, der aus den Korrelationswerten generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b52ae-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="b52ae-123">Werte</span><span class="sxs-lookup"><span data-stu-id="b52ae-123">Values</span></span>|`xs:string`|<span data-ttu-id="b52ae-124">Die Werte, die verwendet wurden, um den Korrelationsinstanzschlüssel zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b52ae-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="b52ae-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="b52ae-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="b52ae-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="b52ae-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="b52ae-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="b52ae-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b52ae-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName".</span><span class="sxs-lookup"><span data-stu-id="b52ae-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b52ae-129">Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b52ae-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b52ae-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b52ae-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b52ae-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b52ae-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
