---
title: ICorDebugProcess::SetThreadContext-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="76af2-102">ICorDebugProcess::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="76af2-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="76af2-103">Legt den Kontext für den angegebenen Thread in diesem Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="76af2-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76af2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76af2-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76af2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="76af2-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="76af2-106">[in] Die ID des Threads für den Kontext festgelegt.</span><span class="sxs-lookup"><span data-stu-id="76af2-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="76af2-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="76af2-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="76af2-108">[in] Ein Array von Bytes, die Kontext des Threads zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="76af2-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="76af2-109">Der Kontext gibt die Architektur des Prozessors auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76af2-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76af2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76af2-110">Remarks</span></span>  
 <span data-ttu-id="76af2-111">Der Debugger sollte diese Methode anstelle der Win32-Aufrufen `SetThreadContext` funktionieren, da der Thread in einem Zustand "manipulierten" tatsächlich möglicherweise in dem Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="76af2-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="76af2-112">Diese Methode sollte verwendet werden, nur wenn ein Thread in systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="76af2-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="76af2-113">Verwendung [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="76af2-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="76af2-114">Es sollte nie den Kontext eines Threads zu ändern, während eines Out-of-Band (OOB) Debug-Ereignisses erforderlich.</span><span class="sxs-lookup"><span data-stu-id="76af2-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="76af2-115">Die übergebenen Daten muss ein Context-Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="76af2-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="76af2-116">Diese Methode kann die Common Language Runtime beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="76af2-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76af2-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="76af2-117">Requirements</span></span>  
 <span data-ttu-id="76af2-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76af2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76af2-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76af2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76af2-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76af2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76af2-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76af2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
