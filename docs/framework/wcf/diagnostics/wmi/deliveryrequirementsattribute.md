---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 7bfc03299fffc8070a7d8a4b3885706ea861bdf6
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2018
ms.locfileid: "50042895"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="9fcf8-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="9fcf8-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="9fcf8-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="9fcf8-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fcf8-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9fcf8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9fcf8-105">Methods</span></span>  
 <span data-ttu-id="9fcf8-106">Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="9fcf8-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9fcf8-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9fcf8-107">Properties</span></span>  
 <span data-ttu-id="9fcf8-108">Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9fcf8-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="9fcf8-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="9fcf8-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="9fcf8-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9fcf8-110">Data type: string</span></span>  
  
 <span data-ttu-id="9fcf8-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9fcf8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9fcf8-112">Gibt an, ob die Bindung eines Diensts Verträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9fcf8-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="9fcf8-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="9fcf8-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="9fcf8-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9fcf8-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9fcf8-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9fcf8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9fcf8-116">Gibt an, ob die Bindung geordnete Nachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9fcf8-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="9fcf8-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="9fcf8-117">TargetContract</span></span>  
 <span data-ttu-id="9fcf8-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9fcf8-118">Data type: string</span></span>  
  
 <span data-ttu-id="9fcf8-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9fcf8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9fcf8-120">Der Vertrag, für den sie gilt.</span><span class="sxs-lookup"><span data-stu-id="9fcf8-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fcf8-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fcf8-121">Requirements</span></span>  
  
|<span data-ttu-id="9fcf8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9fcf8-122">MOF</span></span>|<span data-ttu-id="9fcf8-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9fcf8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9fcf8-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="9fcf8-124">Namespace</span></span>|<span data-ttu-id="9fcf8-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9fcf8-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fcf8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fcf8-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
