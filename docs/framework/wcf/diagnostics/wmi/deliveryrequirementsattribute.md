---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274048"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="2fe98-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="2fe98-102">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="2fe98-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="2fe98-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fe98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fe98-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2fe98-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2fe98-105">Methods</span></span>  

 <span data-ttu-id="2fe98-106">Von der Klasse DeliveryRequirementsAttribute werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="2fe98-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2fe98-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2fe98-107">Properties</span></span>  

 <span data-ttu-id="2fe98-108">Die Klasse DeliveryRequirementsAttribute verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2fe98-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="2fe98-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="2fe98-109">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="2fe98-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="2fe98-110">Data type: string</span></span>  
  
 <span data-ttu-id="2fe98-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2fe98-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2fe98-112">Gibt an, ob die Bindung eines Diensts Verträge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fe98-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="2fe98-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="2fe98-113">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="2fe98-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="2fe98-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="2fe98-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2fe98-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2fe98-116">Gibt an, ob die Bindung geordnete Nachrichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fe98-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="2fe98-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="2fe98-117">TargetContract</span></span>  

 <span data-ttu-id="2fe98-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="2fe98-118">Data type: string</span></span>  
  
 <span data-ttu-id="2fe98-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2fe98-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2fe98-120">Der Vertrag, für den sie gilt.</span><span class="sxs-lookup"><span data-stu-id="2fe98-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fe98-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fe98-121">Requirements</span></span>  
  
|<span data-ttu-id="2fe98-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2fe98-122">MOF</span></span>|<span data-ttu-id="2fe98-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2fe98-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2fe98-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="2fe98-124">Namespace</span></span>|<span data-ttu-id="2fe98-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2fe98-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fe98-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fe98-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
