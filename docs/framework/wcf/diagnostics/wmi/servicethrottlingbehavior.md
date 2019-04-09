---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225494"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="06d04-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="06d04-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="06d04-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="06d04-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06d04-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="06d04-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="06d04-105">Methods</span></span>  
 <span data-ttu-id="06d04-106">Die ServiceThrottlingBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="06d04-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="06d04-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="06d04-107">Properties</span></span>  
 <span data-ttu-id="06d04-108">Die ServiceThrottlingBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="06d04-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="06d04-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="06d04-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="06d04-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="06d04-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="06d04-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="06d04-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06d04-112">Die maximale Anzahl an Nachrichten, die die Verteilerobjekte in einem ServiceHost aktiv verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="06d04-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="06d04-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="06d04-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="06d04-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="06d04-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="06d04-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="06d04-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06d04-116">Die maximale Anzahl der Dienstobjekte, die gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="06d04-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="06d04-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="06d04-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="06d04-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="06d04-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="06d04-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="06d04-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06d04-120">Die maximale Anzahl an Sitzungen, die ein Host gleichzeitig annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="06d04-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d04-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06d04-121">Requirements</span></span>  
  
|<span data-ttu-id="06d04-122">MOF</span><span class="sxs-lookup"><span data-stu-id="06d04-122">MOF</span></span>|<span data-ttu-id="06d04-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="06d04-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="06d04-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="06d04-124">Namespace</span></span>|<span data-ttu-id="06d04-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="06d04-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06d04-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06d04-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
