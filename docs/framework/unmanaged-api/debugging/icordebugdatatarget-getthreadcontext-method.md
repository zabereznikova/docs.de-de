---
title: ICorDebugDataTarget::GetThreadContext-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 44543ca3546827b38643cab0e047032a96be9ea6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="20e9b-102">ICorDebugDataTarget::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="20e9b-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="20e9b-103">Gibt den aktuellen Kontext des Threads für den angegebenen Thread zurück.</span><span class="sxs-lookup"><span data-stu-id="20e9b-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20e9b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20e9b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20e9b-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="20e9b-106">[in] Der Bezeichner des Threads, dessen Kontext abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="20e9b-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="20e9b-107">Der Bezeichner wird vom Betriebssystem definiert.</span><span class="sxs-lookup"><span data-stu-id="20e9b-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="20e9b-108">[in] Eine bitweise Kombination von plattformabhängigen Flags, die angeben, welche Teile des Kontexts gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="20e9b-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="20e9b-109">[in] Die Größe des `pContext`.</span><span class="sxs-lookup"><span data-stu-id="20e9b-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="20e9b-110">[out] Der Puffer, in der Kontext des Threads gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20e9b-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20e9b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20e9b-111">Remarks</span></span>  
 <span data-ttu-id="20e9b-112">Auf Windows-Plattformen `pContext` muss ein `CONTEXT` -Struktur (in "Winnt.h" definiert), die für den Computertyp gemäß geeignet ist die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="20e9b-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="20e9b-113">`contextFlags`benötigen Sie die gleichen Werte wie die `ContextFlags` Feld der `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="20e9b-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="20e9b-114">Die `CONTEXT` Struktur ist prozessorspezifische; die Datei "Winnt.h" Weitere Informationen finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="20e9b-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20e9b-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20e9b-115">Requirements</span></span>  
 <span data-ttu-id="20e9b-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20e9b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20e9b-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20e9b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20e9b-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20e9b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20e9b-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20e9b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e9b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20e9b-120">See Also</span></span>  
 [<span data-ttu-id="20e9b-121">ICorDebugDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20e9b-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="20e9b-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="20e9b-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="20e9b-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="20e9b-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
