---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 98e8a720e92547ca0a893dd988b91cb7907660b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689850"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="e43f3-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="e43f3-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="e43f3-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="e43f3-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e43f3-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e43f3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e43f3-105">Methods</span></span>  
 <span data-ttu-id="e43f3-106">Die ServiceThrottlingBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e43f3-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e43f3-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e43f3-107">Properties</span></span>  
 <span data-ttu-id="e43f3-108">Die ServiceThrottlingBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e43f3-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="e43f3-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="e43f3-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="e43f3-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e43f3-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="e43f3-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e43f3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e43f3-112">Die maximale Anzahl an Nachrichten, die die Verteilerobjekte in einem ServiceHost aktiv verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e43f3-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="e43f3-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="e43f3-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="e43f3-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e43f3-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e43f3-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e43f3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e43f3-116">Die maximale Anzahl der Dienstobjekte, die gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e43f3-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="e43f3-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="e43f3-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="e43f3-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="e43f3-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="e43f3-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e43f3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e43f3-120">Die maximale Anzahl an Sitzungen, die ein Host gleichzeitig annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="e43f3-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43f3-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e43f3-121">Requirements</span></span>  
  
|<span data-ttu-id="e43f3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e43f3-122">MOF</span></span>|<span data-ttu-id="e43f3-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e43f3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e43f3-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="e43f3-124">Namespace</span></span>|<span data-ttu-id="e43f3-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e43f3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e43f3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e43f3-126">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
