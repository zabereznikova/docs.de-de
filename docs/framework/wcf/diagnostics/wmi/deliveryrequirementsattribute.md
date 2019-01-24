---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 809e9d809bce456c831aab83c7ac19a882b2959b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571323"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="37f4d-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="37f4d-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="37f4d-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="37f4d-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37f4d-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="37f4d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="37f4d-105">Methods</span></span>  
 <span data-ttu-id="37f4d-106">Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="37f4d-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="37f4d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="37f4d-107">Properties</span></span>  
 <span data-ttu-id="37f4d-108">Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="37f4d-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="37f4d-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="37f4d-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="37f4d-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="37f4d-110">Data type: string</span></span>  
  
 <span data-ttu-id="37f4d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="37f4d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37f4d-112">Gibt an, ob die Bindung eines Diensts Verträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37f4d-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="37f4d-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="37f4d-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="37f4d-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="37f4d-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="37f4d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="37f4d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37f4d-116">Gibt an, ob die Bindung geordnete Nachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37f4d-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="37f4d-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="37f4d-117">TargetContract</span></span>  
 <span data-ttu-id="37f4d-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="37f4d-118">Data type: string</span></span>  
  
 <span data-ttu-id="37f4d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="37f4d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="37f4d-120">Der Vertrag, für den sie gilt.</span><span class="sxs-lookup"><span data-stu-id="37f4d-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37f4d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37f4d-121">Requirements</span></span>  
  
|<span data-ttu-id="37f4d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="37f4d-122">MOF</span></span>|<span data-ttu-id="37f4d-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="37f4d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="37f4d-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="37f4d-124">Namespace</span></span>|<span data-ttu-id="37f4d-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37f4d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37f4d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37f4d-126">See also</span></span>
- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
