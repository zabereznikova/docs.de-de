---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: edc154fcce0058455f1376a2a45807c92f7f2457
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190949"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="f7f69-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f7f69-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="f7f69-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f7f69-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7f69-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f7f69-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f7f69-105">Methods</span></span>  
 <span data-ttu-id="f7f69-106">Die ServiceThrottlingBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f7f69-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f7f69-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f7f69-107">Properties</span></span>  
 <span data-ttu-id="f7f69-108">Die ServiceThrottlingBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f7f69-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="f7f69-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="f7f69-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="f7f69-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f7f69-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f7f69-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f7f69-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7f69-112">Die maximale Anzahl an Nachrichten, die die Verteilerobjekte in einem ServiceHost aktiv verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f7f69-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="f7f69-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="f7f69-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="f7f69-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f7f69-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f7f69-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f7f69-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7f69-116">Die maximale Anzahl der Dienstobjekte, die gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="f7f69-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="f7f69-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="f7f69-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="f7f69-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="f7f69-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f7f69-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f7f69-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f7f69-120">Die maximale Anzahl an Sitzungen, die ein Host gleichzeitig annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="f7f69-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f69-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7f69-121">Requirements</span></span>  
  
|<span data-ttu-id="f7f69-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f7f69-122">MOF</span></span>|<span data-ttu-id="f7f69-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f7f69-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f7f69-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="f7f69-124">Namespace</span></span>|<span data-ttu-id="f7f69-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f7f69-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7f69-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7f69-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
