---
title: ICLRDebugManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515eb0633c82c3e1386487d1866de79c9898c9cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654606"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="a7bfe-102">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7bfe-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="a7bfe-103">Bietet Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner sowie einen Anzeigenamen zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7bfe-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7bfe-104">Methods</span></span>  
  
|<span data-ttu-id="a7bfe-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-105">Method</span></span>|<span data-ttu-id="a7bfe-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7bfe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7bfe-107">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="a7bfe-108">Stellt eine neue Verbindung zwischen dem Host und den Debugger, einen Bezeichner und einen benutzerfreundlichen Namen Aufgaben zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="a7bfe-109">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="a7bfe-110">Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einen Bezeichner und einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="a7bfe-111">GetDacl-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="a7bfe-112">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="a7bfe-113">IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="a7bfe-114">Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="a7bfe-115">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="a7bfe-116">Ordnet einer Liste von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanzen mit einem Bezeichner und einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="a7bfe-117">SetDacl-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="a7bfe-118">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="a7bfe-119">SetSymbolReadingPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bfe-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="a7bfe-120">Legt die Richtlinie für das Lesen von Programmdatenbankdateien (PDB).</span><span class="sxs-lookup"><span data-stu-id="a7bfe-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="a7bfe-121">Die Richtlinie wird bestimmt, ob Informationen zu Zeilennummern und Dateien in Aufruflisten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7bfe-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7bfe-122">Remarks</span></span>  
 <span data-ttu-id="a7bfe-123">In Debugszenarien, kann ein Host zum Gruppieren von Aufgaben entsprechend der eigenen Programmierlogik möchte.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="a7bfe-124">Eine Gruppierung können z. B. ein Entwickler, die nur die Aufgaben der Entwickler-APIs, anstatt alle Aufgaben, die im Prozess ausgeführt wird, finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="a7bfe-125">`ICLRDebugManager` ermöglicht dem Host, um diese Art der Gruppierung zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7bfe-126">Drei `ICLRDebugManager` Methoden `BeginConnection`, `SetConnectionTasks` und `EndConnection`, voneinander abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="a7bfe-127">Sie müssen in der angegebenen Reihenfolge erwartungsgemäß aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="a7bfe-128">Haben die Gruppierung, und die Bezeichner und den Anzeigenamen, die zur Gruppierung, der Host weist keine Bedeutung für die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a7bfe-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="a7bfe-129">Die CLR übergibt lediglich die Informationen an dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="a7bfe-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7bfe-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7bfe-130">Requirements</span></span>  
 <span data-ttu-id="a7bfe-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7bfe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7bfe-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7bfe-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7bfe-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a7bfe-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7bfe-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7bfe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bfe-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7bfe-135">See also</span></span>
- [<span data-ttu-id="a7bfe-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7bfe-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
