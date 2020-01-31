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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783729"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="7a1ce-102">ICorDebugDataTarget::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="7a1ce-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="7a1ce-103">Gibt den aktuellen Thread Kontext für den angegebenen Thread zurück.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a1ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a1ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a1ce-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7a1ce-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="7a1ce-106">in Der Bezeichner des Threads, dessen Kontext abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="7a1ce-107">Der Bezeichner wird vom Betriebssystem definiert.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="7a1ce-108">in Eine bitweise Kombination von Platt Form abhängigen Flags, die angeben, welche Teile des Kontexts gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="7a1ce-109">[in] Die Größe des `pContext`.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="7a1ce-110">vorgenommen Der Puffer, in dem der Thread Kontext gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a1ce-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a1ce-111">Remarks</span></span>  
 <span data-ttu-id="7a1ce-112">Auf Windows-Plattformen muss `pContext` eine `CONTEXT` Struktur (definiert in "Winnt. h") sein, die für den Computertyp geeignet ist, der durch die [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="7a1ce-113">`contextFlags` müssen die gleichen Werte wie das `ContextFlags` Feld der `CONTEXT` Struktur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7a1ce-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="7a1ce-114">Die `CONTEXT`-Struktur ist Prozessor spezifisch. Ausführliche Informationen finden Sie in der Datei "Winnt. h".</span><span class="sxs-lookup"><span data-stu-id="7a1ce-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a1ce-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a1ce-115">Requirements</span></span>  
 <span data-ttu-id="7a1ce-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a1ce-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a1ce-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a1ce-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a1ce-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a1ce-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a1ce-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a1ce-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1ce-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a1ce-120">See also</span></span>

- [<span data-ttu-id="7a1ce-121">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a1ce-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="7a1ce-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7a1ce-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7a1ce-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7a1ce-123">Debugging</span></span>](index.md)
