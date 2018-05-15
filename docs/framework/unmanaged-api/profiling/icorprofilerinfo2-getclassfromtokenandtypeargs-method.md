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
ms.openlocfilehash: 04be252092732296354cfec102cf8fe648ed2dd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="8783f-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="8783f-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="8783f-103">Ruft die `ClassID` eines Typs mit dem angegebenen Metadaten-Token und die `ClassID` Werte eines beliebigen Typargumente.</span><span class="sxs-lookup"><span data-stu-id="8783f-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8783f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8783f-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8783f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8783f-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="8783f-106">[in] Die ID des Moduls, in dem der Typ befindet.</span><span class="sxs-lookup"><span data-stu-id="8783f-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="8783f-107">[in] Ein `mdTypeDef` Metadatentoken, das auf den Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="8783f-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="8783f-108">[in] Die Anzahl der Typparameter für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="8783f-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="8783f-109">Dieser Wert muss 0 (null) für nicht generische Typen.</span><span class="sxs-lookup"><span data-stu-id="8783f-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="8783f-110">[in] Ein Array von `ClassID` Werten, von denen jeder ein Argument des Typs.</span><span class="sxs-lookup"><span data-stu-id="8783f-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="8783f-111">Der Wert der `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8783f-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="8783f-112">[out] Ein Zeiger auf die `ClassID` des angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="8783f-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8783f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8783f-113">Remarks</span></span>  
 <span data-ttu-id="8783f-114">Aufrufen der `GetClassFromTokenAndTypeArgs` Methode mit einer `mdTypeRef` anstelle von ein `mdTypeDef` Metadatentoken kann unvorhersehbare Folgen haben; Aufrufer sollte sich Auflösen der `mdTypeRef` auf eine `mdTypeDef` bei der Übergabe.</span><span class="sxs-lookup"><span data-stu-id="8783f-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="8783f-115">Wenn der Typ nicht bereits geladen wurde, Aufrufen von `GetClassFromTokenAndTypeArgs` wird geladen, die in vielen Kontexten einen gefährlichen Vorgang wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8783f-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="8783f-116">Beispielsweise kann beim Aufrufen dieser Methode beim Laden von Modulen oder andere Typen zu einer Endlosschleife führen wie die Laufzeitumgebung versucht, Ladevorgänge zirkulär durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8783f-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="8783f-117">Verwenden Sie im Allgemeinen von `GetClassFromTokenAndTypeArgs` wird abgeraten.</span><span class="sxs-lookup"><span data-stu-id="8783f-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="8783f-118">Wenn der Profiler-Ereignisse für einen bestimmten Typ interessiert sind, speichern sie die `ModuleID` und `mdTypeDef` dieses Typs, und verwenden [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) zu überprüfen, ob eine angegebenen `ClassID` ist, mit der die gewünschte Typ.</span><span class="sxs-lookup"><span data-stu-id="8783f-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8783f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8783f-119">Requirements</span></span>  
 <span data-ttu-id="8783f-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8783f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8783f-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8783f-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8783f-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8783f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8783f-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8783f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8783f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8783f-124">See Also</span></span>  
 [<span data-ttu-id="8783f-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8783f-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="8783f-126">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8783f-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
