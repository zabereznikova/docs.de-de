---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 779aabf5ec9b1bca7151eaf781c6dd6f2631b58f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="87fab-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="87fab-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="87fab-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="87fab-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87fab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87fab-104">Syntax</span></span>  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87fab-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="87fab-105">Methods</span></span>  
 <span data-ttu-id="87fab-106">Die ServiceThrottlingBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="87fab-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87fab-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="87fab-107">Properties</span></span>  
 <span data-ttu-id="87fab-108">Die ServiceThrottlingBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="87fab-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="87fab-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="87fab-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="87fab-110">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="87fab-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="87fab-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="87fab-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87fab-112">Die maximale Anzahl an Nachrichten, die die Verteilerobjekte in einem ServiceHost aktiv verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="87fab-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="87fab-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="87fab-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="87fab-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="87fab-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="87fab-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="87fab-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87fab-116">Die maximale Anzahl der Dienstobjekte, die gleichzeitig ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="87fab-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="87fab-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="87fab-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="87fab-118">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="87fab-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="87fab-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="87fab-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87fab-120">Die maximale Anzahl an Sitzungen, die ein Host gleichzeitig annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="87fab-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87fab-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87fab-121">Requirements</span></span>  
  
|<span data-ttu-id="87fab-122">MOF</span><span class="sxs-lookup"><span data-stu-id="87fab-122">MOF</span></span>|<span data-ttu-id="87fab-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="87fab-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87fab-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="87fab-124">Namespace</span></span>|<span data-ttu-id="87fab-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87fab-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87fab-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87fab-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
