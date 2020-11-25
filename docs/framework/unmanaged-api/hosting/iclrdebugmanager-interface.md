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
ms.openlocfilehash: 3836bd349423670a19a19dda67eba75419507a29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724285"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="4688f-102">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4688f-102">ICLRDebugManager Interface</span></span>

<span data-ttu-id="4688f-103">Stellt Methoden bereit, mit denen ein Host eine Reihe von Aufgaben einem Bezeichner und einem anzeigen Amen zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="4688f-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4688f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4688f-104">Methods</span></span>  
  
|<span data-ttu-id="4688f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-105">Method</span></span>|<span data-ttu-id="4688f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4688f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4688f-107">BeginConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-107">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="4688f-108">Stellt eine neue Verbindung zwischen dem Host und dem Debugger her, um Aufgaben einem Bezeichner und einem anzeigen Amen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="4688f-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="4688f-109">EndConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-109">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="4688f-110">Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einem Bezeichner und einem anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="4688f-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="4688f-111">GetDacl-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-111">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="4688f-112">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="4688f-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="4688f-113">IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-113">IsDebuggerAttached Method</span></span>](iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="4688f-114">Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="4688f-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="4688f-115">SetConnectionTasks-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-115">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="4688f-116">Ordnet eine Liste von [ICLRTask](iclrtask-interface.md) -Instanzen einem Bezeichner und einem anzeigen Amen zu.</span><span class="sxs-lookup"><span data-stu-id="4688f-116">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="4688f-117">SetDacl-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-117">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="4688f-118">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="4688f-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="4688f-119">SetSymbolReadingPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="4688f-119">SetSymbolReadingPolicy Method</span></span>](iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="4688f-120">Legt die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) fest.</span><span class="sxs-lookup"><span data-stu-id="4688f-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="4688f-121">Die Richtlinie bestimmt, ob Informationen über Zeilennummern und Dateien in Aufruf Listen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4688f-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4688f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4688f-122">Remarks</span></span>  

 <span data-ttu-id="4688f-123">In Debugszenarien kann ein Host Aufgaben entsprechend seiner eigenen Programmierlogik gruppieren.</span><span class="sxs-lookup"><span data-stu-id="4688f-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="4688f-124">Beispielsweise kann ein Entwickler mit einer Gruppierung nur die Aufgaben anzeigen, die für die Entwickler-APIs erforderlich sind, anstatt jede Aufgabe zu sehen, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4688f-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="4688f-125">`ICLRDebugManager` ermöglicht es dem Host, diese Art von Gruppierung zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4688f-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4688f-126">`ICLRDebugManager`Die drei Methoden `BeginConnection` , `SetConnectionTasks` und `EndConnection` sind voneinander abhängig.</span><span class="sxs-lookup"><span data-stu-id="4688f-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="4688f-127">Sie müssen in der angegebenen Reihenfolge aufgerufen werden, damit Sie erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4688f-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="4688f-128">Die Gruppierung und die Bezeichner und anzeigen Amen, die der Host der Gruppierung zuweist, haben keine Bedeutung für die Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4688f-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="4688f-129">Die CLR übergibt die Informationen lediglich an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="4688f-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4688f-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4688f-130">Requirements</span></span>  

 <span data-ttu-id="4688f-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4688f-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4688f-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4688f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4688f-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4688f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4688f-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4688f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4688f-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4688f-135">See also</span></span>

- [<span data-ttu-id="4688f-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4688f-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
