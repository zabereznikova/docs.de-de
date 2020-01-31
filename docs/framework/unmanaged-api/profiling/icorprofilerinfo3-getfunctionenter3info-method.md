---
title: ICorProfilerInfo3::GetFunctionEnter3Info-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 55411f187e2ef73997633d94b37a7d5d2cfd74c9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868563"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="d214d-102">ICorProfilerInfo3::GetFunctionEnter3Info-Methode</span><span class="sxs-lookup"><span data-stu-id="d214d-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="d214d-103">Stellt den Stapel Rahmen und die Argument Informationen der Funktion bereit, die dem Profiler von der [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Funktion gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="d214d-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="d214d-104">Diese Methode kann nur während des `FunctionEnter3WithInfo`-Rückrufs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d214d-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d214d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d214d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d214d-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="d214d-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d214d-107">[in] Die `FunctionID` der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d214d-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="d214d-108">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="d214d-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="d214d-109">Der Profiler sollte denselben `eltInfo` bereitstellen, der von der [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Funktion angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d214d-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="d214d-110">[out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="d214d-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="d214d-111">Dieses Handle ist nur während des `FunctionEnter3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionEnter3Info`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="d214d-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="d214d-112">[in, out] Ein Zeiger auf die Gesamtgröße (in Bytes) der [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) Struktur (plus alle zusätzlichen [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) Strukturen für die Argument Bereiche, auf die von `pArgumentInfo`verwiesen wird).</span><span class="sxs-lookup"><span data-stu-id="d214d-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="d214d-113">Wenn die angegebene Größe nicht ausreichend ist, wird ERROR_INSUFFICIENT_BUFFER zurückgegeben, und die erwartete Größe wird in `pcbArgumentInfo` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d214d-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="d214d-114">Um `GetFunctionEnter3Info` so aufzurufen, dass nur der erwartete Wert für `*pcbArgumentInfo` abgerufen wird, legen `*pcbArgumentInfo`= 0 und `pArgumentInfo`= NULL fest.</span><span class="sxs-lookup"><span data-stu-id="d214d-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="d214d-115">vorgenommen Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) -Struktur, die die Positionen der Argumente der Funktion im Arbeitsspeicher in der Reihenfolge von links nach rechts beschreibt.</span><span class="sxs-lookup"><span data-stu-id="d214d-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d214d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d214d-116">Remarks</span></span>  
 <span data-ttu-id="d214d-117">Der Profiler muss genügend Speicherplatz für die `COR_PRF_FUNCTION_ARGUMENT_INFO`-Struktur der Funktion reservieren, die geprüft wird, und er muss die Größe im `pcbArgumentInfo`-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="d214d-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d214d-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d214d-118">Requirements</span></span>  
 <span data-ttu-id="d214d-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d214d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d214d-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d214d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d214d-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d214d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d214d-122">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d214d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d214d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d214d-123">See also</span></span>

- [<span data-ttu-id="d214d-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d214d-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="d214d-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d214d-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="d214d-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d214d-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d214d-127">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d214d-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d214d-128">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d214d-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d214d-129">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="d214d-129">Profiling</span></span>](index.md)
