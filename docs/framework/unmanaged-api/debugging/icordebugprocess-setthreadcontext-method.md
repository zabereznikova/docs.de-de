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
ms.openlocfilehash: 5b4052485a6d420eb83578d135ce51f8a918aab0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724519"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="2ebfe-102">ICorDebugProcess::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="2ebfe-102">ICorDebugProcess::SetThreadContext Method</span></span>

<span data-ttu-id="2ebfe-103">Legt den Kontext für den angegebenen Thread in diesem Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ebfe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ebfe-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ebfe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ebfe-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="2ebfe-106">in Die ID des Threads, für den der Kontext festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2ebfe-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="2ebfe-108">in Ein Bytearray, das den Thread Kontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="2ebfe-109">Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ebfe-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ebfe-110">Remarks</span></span>  

 <span data-ttu-id="2ebfe-111">Der Debugger sollte diese Methode anstelle der Win32-Funktion aufzurufen `SetThreadContext` , da der Thread tatsächlich den Zustand "entführt" aufweisen kann, in dem der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="2ebfe-112">Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="2ebfe-113">Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="2ebfe-114">Sie sollten den Kontext eines Threads nie während eines OOB-Debugereignisses (Out-of-Band) ändern.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="2ebfe-115">Die Daten, die übermittelt werden, müssen eine Kontext Struktur für die aktuelle Plattform sein.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="2ebfe-116">Diese Methode kann die Laufzeit beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ebfe-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ebfe-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ebfe-117">Requirements</span></span>  

 <span data-ttu-id="2ebfe-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ebfe-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ebfe-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ebfe-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ebfe-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ebfe-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ebfe-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ebfe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
