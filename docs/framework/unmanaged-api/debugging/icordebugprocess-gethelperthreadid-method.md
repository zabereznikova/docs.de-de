---
title: ICorDebugProcess::GetHelperThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad62b267eb0c49ff8fbefeb45b523c21edc705fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766042"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="1cbb8-102">ICorDebugProcess::GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="1cbb8-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="1cbb8-103">Ruft das Betriebssystem (OS)-Thread-ID des im Debugger das interne Hilfsmethode ab.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cbb8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1cbb8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cbb8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1cbb8-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="1cbb8-106">[out] Ein Zeiger auf das Betriebssystem thread-ID des internen Hilfsthreads des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cbb8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1cbb8-107">Remarks</span></span>  
 <span data-ttu-id="1cbb8-108">Beim Debuggen von verwaltetem und nicht verwaltetem ist es die Verantwortung des Debuggers, um sicherzustellen, dass der Thread mit der angegebenen ID weiterhin ausgeführt wird, wenn ein Haltepunkt eingefügt, die vom Debugger erreicht.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="1cbb8-109">Ein Debugger kann auch dieser Thread vom Benutzer ausblenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="1cbb8-110">Wenn kein Hilfsthread im Prozess noch vorhanden ist die `GetHelperThreadID` Methode gibt 0 (null) in \*`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="1cbb8-111">Sie können nicht die Thread-ID des Threads Hilfsprogramm, zwischenspeichern, da es im Laufe der Zeit ändern kann.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="1cbb8-112">Sie müssen die Thread-ID bei jedem Stoppereignis erneut abfragen.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="1cbb8-113">Die Thread-ID, Hilfsthreads des Debuggers Hilfsthreads ist für jede nicht verwaltete [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) -Ereignis, sodass einen Debugger bestimmen die Thread-ID des Threads Helper und vom Benutzer zu verbergen.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="1cbb8-114">Ein Thread, der als ein Helperthread, während eine nicht verwaltete identifiziert wird `ICorDebugManagedCallback::CreateThread` Ereignis nie verwalteter Benutzercode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cbb8-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1cbb8-115">Requirements</span></span>  
 <span data-ttu-id="1cbb8-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cbb8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cbb8-117">**Header:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="1cbb8-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="1cbb8-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cbb8-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="1cbb8-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cbb8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cbb8-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cbb8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
