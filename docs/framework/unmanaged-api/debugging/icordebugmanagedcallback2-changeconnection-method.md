---
title: ICorDebugManagedCallback2::ChangeConnection-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2ba7e84c11f2fc8619b7046e222a742ee3298554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="45801-102">ICorDebugManagedCallback2::ChangeConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="45801-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="45801-103">Benachrichtigt den Debugger an, dass der Satz von Aufgaben im Zusammenhang mit der angegebenen Verbindung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="45801-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45801-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45801-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45801-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45801-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="45801-106">[in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess, mit der die geänderte Verbindung darstellt.</span><span class="sxs-lookup"><span data-stu-id="45801-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="45801-107">[in] Die ID der Verbindung, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="45801-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45801-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45801-108">Remarks</span></span>  
 <span data-ttu-id="45801-109">Ein `ChangeConnection` Rückruf wird in den folgenden Fällen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="45801-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="45801-110">Wenn Fügt einen Debugger an einen Prozess, der Verbindungen enthält.</span><span class="sxs-lookup"><span data-stu-id="45801-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="45801-111">In diesem Fall die Laufzeit generiert und ein [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) Ereignis und eine `ChangeConnection` Ereignis für jede Verbindung im Prozess.</span><span class="sxs-lookup"><span data-stu-id="45801-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="45801-112">Ein `ChangeConnection` Ereignis wird generiert, für jede vorhandene Verbindung, unabhängig davon, ob diese Verbindung Satz von Aufgaben seit seiner Erstellung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="45801-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="45801-113">Wenn ein Host ruft [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in der [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="45801-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="45801-114">Der Debugger sollten alle Threads im Prozess kann die neuen Änderungen übernehmen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="45801-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45801-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45801-115">Requirements</span></span>  
 <span data-ttu-id="45801-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45801-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45801-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45801-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45801-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45801-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45801-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45801-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45801-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45801-120">See Also</span></span>  
 [<span data-ttu-id="45801-121">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45801-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="45801-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45801-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
