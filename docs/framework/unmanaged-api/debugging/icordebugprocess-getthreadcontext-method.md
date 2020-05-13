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
ms.openlocfilehash: 2bdbf373144e2fb49074cfd035e7b0ffe3c8c291
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212886"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="f5164-102">ICorDebugProcess::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f5164-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="f5164-103">Ruft den Kontext für den angegebenen Thread in diesem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f5164-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5164-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5164-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5164-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5164-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f5164-106">in Die ID des Threads, für den der Kontext abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f5164-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f5164-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f5164-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="f5164-108">[in, out] Ein Bytearray, das den Thread Kontext beschreibt.</span><span class="sxs-lookup"><span data-stu-id="f5164-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="f5164-109">Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f5164-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5164-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5164-110">Remarks</span></span>  
 <span data-ttu-id="f5164-111">Der Debugger sollte diese Methode anstelle der Win32-Methode anstelle der Win32- `GetThreadContext` Methode abrufen, da sich der Thread möglicherweise im Zustand "entführt" befindet, in dem der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f5164-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="f5164-112">Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet.</span><span class="sxs-lookup"><span data-stu-id="f5164-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="f5164-113">Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="f5164-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="f5164-114">Die zurückgegebenen Daten sind eine Kontext Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="f5164-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="f5164-115">Genau wie bei der Win32- `GetThreadContext` Methode sollte der Aufrufer den- `context` Parameter vor dem Aufrufen dieser Methode initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f5164-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5164-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f5164-116">Requirements</span></span>  
 <span data-ttu-id="f5164-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5164-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5164-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5164-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5164-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5164-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5164-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5164-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
