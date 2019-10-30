---
title: ICorDebugDataTarget::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 278320391615eddaa8ba878ef87f802f30cddb95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122023"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="b387c-102">ICorDebugDataTarget::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="b387c-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="b387c-103">Gibt den aktuellen Thread Kontext für den angegebenen Thread zurück.</span><span class="sxs-lookup"><span data-stu-id="b387c-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b387c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b387c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b387c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b387c-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="b387c-106">in Der Bezeichner des Threads, dessen Kontext abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b387c-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="b387c-107">Der Bezeichner wird vom Betriebssystem definiert.</span><span class="sxs-lookup"><span data-stu-id="b387c-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="b387c-108">in Eine bitweise Kombination von Platt Form abhängigen Flags, die angeben, welche Teile des Kontexts gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b387c-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="b387c-109">[in] Die Größe des `pContext`.</span><span class="sxs-lookup"><span data-stu-id="b387c-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="b387c-110">vorgenommen Der Puffer, in dem der Thread Kontext gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="b387c-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b387c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b387c-111">Remarks</span></span>  
 <span data-ttu-id="b387c-112">Auf Windows-Plattformen muss `pContext` eine `CONTEXT` Struktur (definiert in "Winnt. h") sein, die für den Computertyp geeignet ist, der durch die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) -Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b387c-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="b387c-113">`contextFlags` müssen die gleichen Werte wie das `ContextFlags` Feld der `CONTEXT` Struktur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b387c-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="b387c-114">Die `CONTEXT`-Struktur ist Prozessor spezifisch. Ausführliche Informationen finden Sie in der Datei "Winnt. h".</span><span class="sxs-lookup"><span data-stu-id="b387c-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b387c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b387c-115">Requirements</span></span>  
 <span data-ttu-id="b387c-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b387c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b387c-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b387c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b387c-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b387c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b387c-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b387c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b387c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b387c-120">See also</span></span>

- [<span data-ttu-id="b387c-121">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b387c-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="b387c-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b387c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b387c-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b387c-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
