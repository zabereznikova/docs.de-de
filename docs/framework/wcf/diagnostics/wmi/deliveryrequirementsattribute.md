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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40bdc27337daae02795137fc3ac67575787018c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="b7510-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="b7510-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="b7510-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="b7510-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7510-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7510-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b7510-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b7510-105">Methods</span></span>  
 <span data-ttu-id="b7510-106">Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="b7510-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b7510-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b7510-107">Properties</span></span>  
 <span data-ttu-id="b7510-108">Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b7510-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="b7510-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="b7510-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="b7510-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b7510-110">Data type: string</span></span>  
  
 <span data-ttu-id="b7510-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b7510-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7510-112">Gibt an, ob die Bindung eines Diensts Verträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b7510-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="b7510-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="b7510-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="b7510-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b7510-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b7510-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b7510-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7510-116">Gibt an, ob die Bindung geordnete Nachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b7510-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="b7510-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="b7510-117">TargetContract</span></span>  
 <span data-ttu-id="b7510-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b7510-118">Data type: string</span></span>  
  
 <span data-ttu-id="b7510-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b7510-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7510-120">Der Vertrag, für den sie gilt.</span><span class="sxs-lookup"><span data-stu-id="b7510-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7510-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7510-121">Requirements</span></span>  
  
|<span data-ttu-id="b7510-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b7510-122">MOF</span></span>|<span data-ttu-id="b7510-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b7510-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b7510-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="b7510-124">Namespace</span></span>|<span data-ttu-id="b7510-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b7510-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7510-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7510-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
