---
title: ICorDebugProcess::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 41c5116d23655730f3586dc656aa69c8ae817b6c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792626"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="7e46a-102">ICorDebugProcess::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="7e46a-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="7e46a-103">Ruft den Kontext für den angegebenen Thread in diesem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="7e46a-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e46a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e46a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e46a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7e46a-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="7e46a-106">in Die ID des Threads, für den der Kontext abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e46a-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="7e46a-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="7e46a-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="7e46a-108">[in, out] Ein Bytearray, das den Thread Kontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="7e46a-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="7e46a-109">Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7e46a-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e46a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e46a-110">Remarks</span></span>  
 <span data-ttu-id="7e46a-111">Der Debugger sollte diese Methode anstelle der Win32-`GetThreadContext`-Methode aufzurufen, da der Thread tatsächlich den Zustand "entführt" aufweisen kann, in dem der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e46a-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="7e46a-112">Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet.</span><span class="sxs-lookup"><span data-stu-id="7e46a-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="7e46a-113">Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="7e46a-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="7e46a-114">Die zurückgegebenen Daten sind eine Kontext Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="7e46a-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="7e46a-115">Ebenso wie bei der Win32-`GetThreadContext` Methode sollte der Aufrufer den `context`-Parameter initialisieren, bevor diese Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7e46a-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e46a-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e46a-116">Requirements</span></span>  
 <span data-ttu-id="7e46a-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e46a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e46a-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e46a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e46a-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e46a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e46a-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e46a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
