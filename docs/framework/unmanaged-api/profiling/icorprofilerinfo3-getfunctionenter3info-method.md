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
ms.openlocfilehash: 50d16b8036144d6ede349149fa4ae37344064d8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177019"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="3b85f-102">ICorProfilerInfo3::GetFunctionEnter3Info-Methode</span><span class="sxs-lookup"><span data-stu-id="3b85f-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="3b85f-103">Stellt den Stapelrahmen und die Argumentinformationen der Funktion bereit, die dem Profiler von der [Funktion FunctionEnter3WithInfo](functionenter3withinfo-function.md) gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="3b85f-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="3b85f-104">Diese Methode kann nur während des `FunctionEnter3WithInfo`-Rückrufs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3b85f-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b85f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b85f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b85f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b85f-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="3b85f-107">[in] Die `FunctionID` der Funktion, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3b85f-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="3b85f-108">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="3b85f-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="3b85f-109">Der Profiler sollte `eltInfo` dasselbe bereitstellen, was er von der [Funktion FunctionEnter3WithInfo](functionenter3withinfo-function.md) gegeben hat.</span><span class="sxs-lookup"><span data-stu-id="3b85f-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="3b85f-110">[out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="3b85f-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="3b85f-111">Dieses Handle ist nur während des `FunctionEnter3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionEnter3Info`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="3b85f-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="3b85f-112">[in, out] Ein Zeiger auf die Gesamtgröße der [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) Struktur (plus zusätzliche [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) Strukturen für `pArgumentInfo`die Argumentbereiche, auf die von ) verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3b85f-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="3b85f-113">Wenn die angegebene Größe nicht ausreichend ist, wird ERROR_INSUFFICIENT_BUFFER zurückgegeben, und die erwartete Größe wird in `pcbArgumentInfo` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3b85f-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="3b85f-114">Um `GetFunctionEnter3Info` so aufzurufen, dass nur der erwartete Wert für `*pcbArgumentInfo` abgerufen wird, legen `*pcbArgumentInfo`= 0 und `pArgumentInfo`= NULL fest.</span><span class="sxs-lookup"><span data-stu-id="3b85f-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="3b85f-115">[out] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) Struktur, die die Positionen der Argumente der Funktion im Speicher in links nach rechts beschreibt.</span><span class="sxs-lookup"><span data-stu-id="3b85f-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b85f-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3b85f-116">Remarks</span></span>  
 <span data-ttu-id="3b85f-117">Der Profiler muss genügend Speicherplatz für die `COR_PRF_FUNCTION_ARGUMENT_INFO`-Struktur der Funktion reservieren, die geprüft wird, und er muss die Größe im `pcbArgumentInfo`-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="3b85f-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b85f-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3b85f-118">Requirements</span></span>  
 <span data-ttu-id="3b85f-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b85f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b85f-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b85f-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b85f-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b85f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b85f-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b85f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b85f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b85f-123">See also</span></span>

- [<span data-ttu-id="3b85f-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b85f-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="3b85f-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b85f-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="3b85f-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b85f-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="3b85f-127">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b85f-127">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="3b85f-128">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3b85f-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3b85f-129">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="3b85f-129">Profiling</span></span>](index.md)
