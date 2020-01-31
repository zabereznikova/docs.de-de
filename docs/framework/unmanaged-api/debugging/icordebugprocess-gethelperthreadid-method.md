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
ms.openlocfilehash: d0dc301c67d09ebb15bf47cef15e642fb7c78fb9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792604"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="a8c28-102">ICorDebugProcess::GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="a8c28-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="a8c28-103">Ruft die ID des Betriebssystems (OS) des internen Hilfsthreads des Debuggers ab.</span><span class="sxs-lookup"><span data-stu-id="a8c28-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8c28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8c28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8c28-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a8c28-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="a8c28-106">vorgenommen Ein Zeiger auf die Betriebssystem Thread-ID des internen Hilfsthreads des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="a8c28-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8c28-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8c28-107">Remarks</span></span>  
 <span data-ttu-id="a8c28-108">Beim verwalteten und nicht verwalteten Debuggen ist es für den Debugger zuständig, sicherzustellen, dass der Thread mit der angegebenen ID weiterhin ausgeführt wird, wenn er einen Haltepunkt erreicht, der vom Debugger platziert wird.</span><span class="sxs-lookup"><span data-stu-id="a8c28-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="a8c28-109">Ein Debugger möchte möglicherweise auch diesen Thread vom Benutzer ausblenden.</span><span class="sxs-lookup"><span data-stu-id="a8c28-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="a8c28-110">Wenn noch kein Hilfsthread im Prozess vorhanden ist, gibt die `GetHelperThreadID`-Methode in \*`pThreadID`NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="a8c28-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="a8c28-111">Die Thread-ID des hilfsobreads kann nicht zwischengespeichert werden, da Sie sich im Laufe der Zeit ändern kann.</span><span class="sxs-lookup"><span data-stu-id="a8c28-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="a8c28-112">Sie müssen die Thread-ID bei jedem anhalteereignis erneut Abfragen.</span><span class="sxs-lookup"><span data-stu-id="a8c28-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="a8c28-113">Die Thread-ID des Hilfsthreads des Debuggers ist bei jedem nicht verwalteten [ICorDebugManagedCallback:: foratethread](icordebugmanagedcallback-createthread-method.md) -Ereignis richtig, sodass ein Debugger die Thread-ID seines hilfsobreads ermitteln und vom Benutzer ausblenden kann.</span><span class="sxs-lookup"><span data-stu-id="a8c28-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="a8c28-114">Ein Thread, der während eines nicht verwalteten `ICorDebugManagedCallback::CreateThread` Ereignisses als Hilfsthread identifiziert wird, führt niemals verwalteten Benutzercode aus.</span><span class="sxs-lookup"><span data-stu-id="a8c28-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8c28-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8c28-115">Requirements</span></span>  
 <span data-ttu-id="a8c28-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8c28-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8c28-117">**Header:** "Cordebug. idl".</span><span class="sxs-lookup"><span data-stu-id="a8c28-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="a8c28-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8c28-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="a8c28-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8c28-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8c28-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8c28-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
