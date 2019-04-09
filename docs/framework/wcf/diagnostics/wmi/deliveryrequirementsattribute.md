---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101776"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="a32c9-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="a32c9-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="a32c9-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="a32c9-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a32c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a32c9-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a32c9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a32c9-105">Methods</span></span>  
 <span data-ttu-id="a32c9-106">Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a32c9-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a32c9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a32c9-107">Properties</span></span>  
 <span data-ttu-id="a32c9-108">Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a32c9-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="a32c9-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="a32c9-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="a32c9-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a32c9-110">Data type: string</span></span>  
  
 <span data-ttu-id="a32c9-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a32c9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a32c9-112">Gibt an, ob die Bindung eines Diensts Verträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a32c9-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="a32c9-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="a32c9-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="a32c9-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="a32c9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="a32c9-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a32c9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a32c9-116">Gibt an, ob die Bindung geordnete Nachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a32c9-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="a32c9-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="a32c9-117">TargetContract</span></span>  
 <span data-ttu-id="a32c9-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="a32c9-118">Data type: string</span></span>  
  
 <span data-ttu-id="a32c9-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a32c9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a32c9-120">Der Vertrag, für den sie gilt.</span><span class="sxs-lookup"><span data-stu-id="a32c9-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a32c9-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a32c9-121">Requirements</span></span>  
  
|<span data-ttu-id="a32c9-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a32c9-122">MOF</span></span>|<span data-ttu-id="a32c9-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a32c9-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a32c9-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="a32c9-124">Namespace</span></span>|<span data-ttu-id="a32c9-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a32c9-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a32c9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a32c9-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
