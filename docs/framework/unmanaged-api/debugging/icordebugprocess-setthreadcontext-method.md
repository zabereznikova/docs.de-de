---
title: ICorDebugProcess::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 3c57021061c1566b369cdd43847e3994cf54e2da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139673"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="c836e-102">ICorDebugProcess::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="c836e-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="c836e-103">Legt den Kontext für den angegebenen Thread in diesem Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="c836e-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c836e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c836e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c836e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c836e-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c836e-106">in Die ID des Threads, für den der Kontext festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c836e-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c836e-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="c836e-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="c836e-108">in Ein Bytearray, das den Thread Kontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c836e-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="c836e-109">Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c836e-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c836e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c836e-110">Remarks</span></span>  
 <span data-ttu-id="c836e-111">Der Debugger sollte diese Methode anstelle der Win32-`SetThreadContext`-Funktion aufzurufen, da der Thread tatsächlich den Zustand "entführt" aufweisen kann, in dem der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c836e-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="c836e-112">Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet.</span><span class="sxs-lookup"><span data-stu-id="c836e-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="c836e-113">Verwenden Sie [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c836e-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="c836e-114">Sie sollten den Kontext eines Threads nie während eines OOB-Debugereignisses (Out-of-Band) ändern.</span><span class="sxs-lookup"><span data-stu-id="c836e-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="c836e-115">Die Daten, die übermittelt werden, müssen eine Kontext Struktur für die aktuelle Plattform sein.</span><span class="sxs-lookup"><span data-stu-id="c836e-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="c836e-116">Diese Methode kann die Laufzeit beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c836e-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c836e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c836e-117">Requirements</span></span>  
 <span data-ttu-id="c836e-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c836e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c836e-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c836e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c836e-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c836e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c836e-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c836e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
