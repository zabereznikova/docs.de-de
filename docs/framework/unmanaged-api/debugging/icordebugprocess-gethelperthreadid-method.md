---
title: ICorDebugProcess::GetHelperThreadID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03e801cb58b8f5c3f658085fcee4288278e545c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="15e1c-102">ICorDebugProcess::GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="15e1c-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="15e1c-103">Ruft das Betriebssystem (BS)-Thread-ID des internen Hilfsthreads des Debuggers an.</span><span class="sxs-lookup"><span data-stu-id="15e1c-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15e1c-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15e1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15e1c-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="15e1c-106">[out] Ein Zeiger auf das Betriebssystem thread-ID des internen Hilfsthreads des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="15e1c-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15e1c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15e1c-107">Remarks</span></span>  
 <span data-ttu-id="15e1c-108">Beim Debuggen von verwaltetem und nicht verwaltetem ist es der Debugger dafür verantwortlich, um sicherzustellen, dass der Thread mit der angegebenen ID weiterhin ausgeführt wird, wenn sie einen Haltepunkt vom Debugger platziert erreichen.</span><span class="sxs-lookup"><span data-stu-id="15e1c-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="15e1c-109">Ein Debugger kann auch dieses Threads vom Benutzer ausblenden möchten.</span><span class="sxs-lookup"><span data-stu-id="15e1c-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="15e1c-110">Wenn keine Hilfs-Thread im Prozess noch vorhanden ist die `GetHelperThreadID` Methodenrückgabe 0 (null) in *`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="15e1c-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in *`pThreadID`.</span></span>  
  
 <span data-ttu-id="15e1c-111">Die Thread-ID des Threads Hilfsprogramm kann nicht zwischengespeichert werden, da er im Laufe der Zeit ändern kann.</span><span class="sxs-lookup"><span data-stu-id="15e1c-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="15e1c-112">Sie müssen das Thread-ID bei jeder Stopping-Ereignis erneut abfragen.</span><span class="sxs-lookup"><span data-stu-id="15e1c-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="15e1c-113">Die Thread-ID, Hilfsthreads des Debuggers wird auf korrekt sein, jede nicht verwaltete [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) Ereignis, sodass einen Debugger bestimmen die Thread-ID seines Hilfsthreads und vom Benutzer zu verbergen.</span><span class="sxs-lookup"><span data-stu-id="15e1c-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="15e1c-114">Ein Thread, der als Hilfsthread, während ein nicht verwaltetes identifiziert wird `ICorDebugManagedCallback::CreateThread` Ereignis verwalteter Benutzercode nie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15e1c-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15e1c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15e1c-115">Requirements</span></span>  
 <span data-ttu-id="15e1c-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15e1c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15e1c-117">**Header:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="15e1c-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="15e1c-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15e1c-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="15e1c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15e1c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15e1c-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15e1c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
