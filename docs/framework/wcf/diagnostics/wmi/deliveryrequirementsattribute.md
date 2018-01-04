---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e297bfc0499ea3ee8d3dd8395165ca22b2baa1de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="7630b-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="7630b-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="7630b-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="7630b-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7630b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7630b-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7630b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7630b-105">Methods</span></span>  
 <span data-ttu-id="7630b-106">Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="7630b-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7630b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7630b-107">Properties</span></span>  
 <span data-ttu-id="7630b-108">Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7630b-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="7630b-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="7630b-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="7630b-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7630b-110">Data type: string</span></span>  
  
 <span data-ttu-id="7630b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7630b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7630b-112">Gibt an, ob die Bindung eines Diensts Verträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7630b-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="7630b-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="7630b-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="7630b-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7630b-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="7630b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7630b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7630b-116">Gibt an, ob die Bindung geordnete Nachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7630b-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="7630b-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="7630b-117">TargetContract</span></span>  
 <span data-ttu-id="7630b-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7630b-118">Data type: string</span></span>  
  
 <span data-ttu-id="7630b-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7630b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7630b-120">Der Vertrag, für den sie gilt.</span><span class="sxs-lookup"><span data-stu-id="7630b-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7630b-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7630b-121">Requirements</span></span>  
  
|<span data-ttu-id="7630b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7630b-122">MOF</span></span>|<span data-ttu-id="7630b-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7630b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7630b-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="7630b-124">Namespace</span></span>|<span data-ttu-id="7630b-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7630b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7630b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7630b-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
