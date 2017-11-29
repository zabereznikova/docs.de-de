---
title: ICorDebugManagedCallback2::ChangeConnection-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="a68a3-102">ICorDebugManagedCallback2::ChangeConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="a68a3-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="a68a3-103">Benachrichtigt den Debugger an, dass der Satz von Aufgaben im Zusammenhang mit der angegebenen Verbindung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="a68a3-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a68a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a68a3-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a68a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a68a3-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a68a3-106">[in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess, mit der die geänderte Verbindung darstellt.</span><span class="sxs-lookup"><span data-stu-id="a68a3-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="a68a3-107">[in] Die ID der Verbindung, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a68a3-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a68a3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a68a3-108">Remarks</span></span>  
 <span data-ttu-id="a68a3-109">Ein `ChangeConnection` Rückruf wird in den folgenden Fällen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="a68a3-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="a68a3-110">Wenn Fügt einen Debugger an einen Prozess, der Verbindungen enthält.</span><span class="sxs-lookup"><span data-stu-id="a68a3-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="a68a3-111">In diesem Fall die Laufzeit generiert und ein [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) Ereignis und eine `ChangeConnection` Ereignis für jede Verbindung im Prozess.</span><span class="sxs-lookup"><span data-stu-id="a68a3-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="a68a3-112">Ein `ChangeConnection` Ereignis wird generiert, für jede vorhandene Verbindung, unabhängig davon, ob diese Verbindung Satz von Aufgaben seit seiner Erstellung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="a68a3-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="a68a3-113">Wenn ein Host ruft [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in der [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="a68a3-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="a68a3-114">Der Debugger sollten alle Threads im Prozess kann die neuen Änderungen übernehmen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a68a3-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a68a3-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a68a3-115">Requirements</span></span>  
 <span data-ttu-id="a68a3-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a68a3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a68a3-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a68a3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a68a3-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a68a3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a68a3-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a68a3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68a3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a68a3-120">See Also</span></span>  
 [<span data-ttu-id="a68a3-121">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a68a3-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="a68a3-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a68a3-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
