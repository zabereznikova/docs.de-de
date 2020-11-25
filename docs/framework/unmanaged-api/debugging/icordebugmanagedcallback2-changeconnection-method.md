---
title: ICorDebugManagedCallback2::ChangeConnection-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 4ba04b1a4815587b40d03819fdac795dcc7f2c4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697271"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="654af-102">ICorDebugManagedCallback2::ChangeConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="654af-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>

<span data-ttu-id="654af-103">Benachrichtigt den Debugger, dass sich der Satz der Tasks, die der angegebenen Verbindung zugeordnet sind, geändert hat.</span><span class="sxs-lookup"><span data-stu-id="654af-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="654af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="654af-104">Syntax</span></span>  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="654af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="654af-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="654af-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der die geänderte Verbindung enthält.</span><span class="sxs-lookup"><span data-stu-id="654af-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="654af-107">in Die ID der Verbindung, die geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="654af-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="654af-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="654af-108">Remarks</span></span>  

 <span data-ttu-id="654af-109">Ein `ChangeConnection` Rückruf wird in einem der folgenden Fälle ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="654af-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="654af-110">Wenn ein Debugger an einen Prozess angefügt wird, der Verbindungen enthält.</span><span class="sxs-lookup"><span data-stu-id="654af-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="654af-111">In diesem Fall generiert und versendet die Common Language Runtime ein [ICorDebugManagedCallback2:: forateconnetction](icordebugmanagedcallback2-createconnection-method.md) -Ereignis und ein- `ChangeConnection` Ereignis für jede Verbindung im Prozess.</span><span class="sxs-lookup"><span data-stu-id="654af-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="654af-112">Ein `ChangeConnection` -Ereignis wird für jede vorhandene Verbindung generiert, unabhängig davon, ob der Satz von Tasks der Verbindung seit seiner Erstellung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="654af-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="654af-113">Wenn ein Host [ICLRDebugManager:: SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) in der [Hosting-API](../hosting/index.md)aufruft.</span><span class="sxs-lookup"><span data-stu-id="654af-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
 <span data-ttu-id="654af-114">Der Debugger sollte alle Threads im Prozess Scannen, um die neuen Änderungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="654af-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="654af-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="654af-115">Requirements</span></span>  

 <span data-ttu-id="654af-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="654af-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="654af-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="654af-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="654af-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="654af-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="654af-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="654af-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="654af-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="654af-120">See also</span></span>

- [<span data-ttu-id="654af-121">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="654af-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="654af-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="654af-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
