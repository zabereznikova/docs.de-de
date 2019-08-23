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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c133338ec0edac19f49d435df41e3081c486f51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948465"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="713e8-102">ICorProfilerInfo4::GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="713e8-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="713e8-103">Ordnet einen Anweisungs Zeiger für verwalteten Code der JIT-neu kompilierten Version einer Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="713e8-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="713e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="713e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="713e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="713e8-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="713e8-106">in Der Anweisungs Zeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="713e8-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="713e8-107">vorgenommen Die Funktions-ID.</span><span class="sxs-lookup"><span data-stu-id="713e8-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="713e8-108">vorgenommen Die Identität der neu kompilierten JIT-Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="713e8-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="713e8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="713e8-109">Remarks</span></span>  
 <span data-ttu-id="713e8-110">`GetFunctionFromIP2`ähnelt `GetFunctionFromIP`, mit der Ausnahme, dass die JIT-kompilierte ID anstelle der Funktions-ID der Funktion abgerufen wird, die die angegebene IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="713e8-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="713e8-111">`GetFunctionFromIP2`kann eine Garbage Collection auslöst, während `GetFunctionFromIP` dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="713e8-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="713e8-112">Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="713e8-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="713e8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="713e8-113">Requirements</span></span>  
 <span data-ttu-id="713e8-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="713e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="713e8-115">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="713e8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="713e8-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="713e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="713e8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="713e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="713e8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="713e8-118">See also</span></span>

- [<span data-ttu-id="713e8-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="713e8-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
