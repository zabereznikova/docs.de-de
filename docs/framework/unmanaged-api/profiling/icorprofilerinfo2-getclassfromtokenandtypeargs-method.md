---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a88a6c19a5c8b45576dd6f632adf70f7ec2eed55
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751874"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="c7500-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="c7500-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="c7500-103">Ruft die `ClassID` eines Typs mit dem Token der angegebenen Metadaten und die `ClassID` Werte aller Typargumente.</span><span class="sxs-lookup"><span data-stu-id="c7500-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7500-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7500-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7500-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7500-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c7500-106">[in] Die ID des Moduls, in dem der Typ befindet.</span><span class="sxs-lookup"><span data-stu-id="c7500-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="c7500-107">[in] Ein `mdTypeDef` Metadatentoken, das den Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="c7500-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c7500-108">[in] Die Anzahl der Typparameter für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="c7500-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="c7500-109">Dieser Wert muss 0 (null) für nicht generische Typen sein.</span><span class="sxs-lookup"><span data-stu-id="c7500-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c7500-110">[in] Ein Array von `ClassID` Werten, von denen jeder ein Argument des Typs.</span><span class="sxs-lookup"><span data-stu-id="c7500-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="c7500-111">Der Wert des `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c7500-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="c7500-112">[out] Ein Zeiger auf die `ClassID` des angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="c7500-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7500-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7500-113">Remarks</span></span>  
 <span data-ttu-id="c7500-114">Aufrufen der `GetClassFromTokenAndTypeArgs` -Methode mit einer `mdTypeRef` anstelle von eine `mdTypeDef` Metadatentoken unvorhersehbare Ergebnisse haben; der Aufrufer sollte sich Auflösen der `mdTypeRef` auf ein `mdTypeDef` bei der Übergabe.</span><span class="sxs-lookup"><span data-stu-id="c7500-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="c7500-115">Wenn der Typ nicht bereits geladen ist, wird beim Aufrufen `GetClassFromTokenAndTypeArgs` löst laden, die in vielen Kontexten einen gefährlichen Vorgang ist.</span><span class="sxs-lookup"><span data-stu-id="c7500-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="c7500-116">Beispielsweise kann das Aufrufen dieser Methode während des Ladens von Modulen oder andere Typen zu einer Endlosschleife führen wie die Laufzeit versucht, die Ladevorgänge zirkulär durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="c7500-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="c7500-117">Im Allgemeinen die Verwendung von `GetClassFromTokenAndTypeArgs` wird abgeraten.</span><span class="sxs-lookup"><span data-stu-id="c7500-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="c7500-118">Wenn Profiler Ereignissen für einen bestimmten Typ interessiert sind, sollten sie Speichern der `ModuleID` und `mdTypeDef` dieses Typs, und verwenden [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) überprüfen, ob eine angegebene `ClassID` ist, die von der gewünschte Typ.</span><span class="sxs-lookup"><span data-stu-id="c7500-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7500-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7500-119">Requirements</span></span>  
 <span data-ttu-id="c7500-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7500-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7500-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7500-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7500-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7500-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7500-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7500-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7500-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7500-124">See also</span></span>

- [<span data-ttu-id="c7500-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7500-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c7500-126">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7500-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
