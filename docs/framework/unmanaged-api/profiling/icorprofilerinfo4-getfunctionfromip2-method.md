---
title: ICorProfilerInfo4::GetFunctionFromIP2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
ms.openlocfilehash: 8ad04a7a6705b961686317c9473b885fb90676ce
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861917"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="7fb4a-102">ICorProfilerInfo4::GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="7fb4a-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="7fb4a-103">Ordnet einen Anweisungs Zeiger für verwalteten Code der JIT-neu kompilierten Version einer Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="7fb4a-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fb4a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fb4a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7fb4a-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="7fb4a-106">in Der Anweisungs Zeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="7fb4a-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="7fb4a-107">vorgenommen Die Funktions-ID.</span><span class="sxs-lookup"><span data-stu-id="7fb4a-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="7fb4a-108">vorgenommen Die Identität der neu kompilierten JIT-Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="7fb4a-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fb4a-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fb4a-109">Remarks</span></span>  
 <span data-ttu-id="7fb4a-110">`GetFunctionFromIP2` ähnelt `GetFunctionFromIP`, mit dem Unterschied, dass die JIT-kompilierte ID anstelle der Funktions-ID der Funktion, die die angegebene IP-Adresse enthält, abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7fb4a-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fb4a-111">`GetFunctionFromIP2` können eine Garbage Collection auslöst, während `GetFunctionFromIP` nicht.</span><span class="sxs-lookup"><span data-stu-id="7fb4a-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="7fb4a-112">Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="7fb4a-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fb4a-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fb4a-113">Requirements</span></span>  
 <span data-ttu-id="7fb4a-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fb4a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb4a-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fb4a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fb4a-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fb4a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fb4a-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fb4a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb4a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fb4a-118">See also</span></span>

- [<span data-ttu-id="7fb4a-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fb4a-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
