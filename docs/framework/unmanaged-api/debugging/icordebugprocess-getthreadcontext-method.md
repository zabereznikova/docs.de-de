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
ms.openlocfilehash: 3be689e5c1474bcbfbca72a14a298762dc2e7a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724545"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="1aa6c-102">ICorDebugProcess::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="1aa6c-102">ICorDebugProcess::GetThreadContext Method</span></span>

<span data-ttu-id="1aa6c-103">Ruft den Kontext für den angegebenen Thread in diesem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1aa6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1aa6c-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="1aa6c-106">in Die ID des Threads, für den der Kontext abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="1aa6c-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="1aa6c-108">[in, out] Ein Bytearray, das den Thread Kontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="1aa6c-109">Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aa6c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1aa6c-110">Remarks</span></span>  

 <span data-ttu-id="1aa6c-111">Der Debugger sollte diese Methode anstelle der Win32-Methode anstelle der Win32- `GetThreadContext` Methode abrufen, da sich der Thread möglicherweise im Zustand "entführt" befindet, in dem der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="1aa6c-112">Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="1aa6c-113">Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="1aa6c-114">Die zurückgegebenen Daten sind eine Kontext Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="1aa6c-115">Genau wie bei der Win32- `GetThreadContext` Methode sollte der Aufrufer den- `context` Parameter vor dem Aufrufen dieser Methode initialisieren.</span><span class="sxs-lookup"><span data-stu-id="1aa6c-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa6c-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1aa6c-116">Requirements</span></span>  

 <span data-ttu-id="1aa6c-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa6c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa6c-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1aa6c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1aa6c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aa6c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aa6c-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa6c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
