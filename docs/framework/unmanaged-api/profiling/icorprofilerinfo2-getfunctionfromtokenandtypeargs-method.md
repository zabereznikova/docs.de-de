---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bc89ca6213008192c0af8e519ae255c13e9763c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="62c01-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="62c01-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="62c01-103">Ruft die `FunctionID` einer Funktion mit dem angegebenen Metadaten-Token, mit der Klasse, und `ClassID` Werte eines beliebigen Typargumente.</span><span class="sxs-lookup"><span data-stu-id="62c01-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62c01-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62c01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62c01-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="62c01-106">[in] Die ID des Moduls, in dem die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="62c01-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="62c01-107">[in] Ein `mdMethodDef` Metadatentoken, das die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="62c01-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="62c01-108">[in] Die ID der enthaltenden Klasse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="62c01-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="62c01-109">[in] Die Anzahl der Typparameter für die angegebene Funktion.</span><span class="sxs-lookup"><span data-stu-id="62c01-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="62c01-110">Dieser Wert muss 0 (null) für nicht generische Funktionen sein.</span><span class="sxs-lookup"><span data-stu-id="62c01-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="62c01-111">[in] Ein Array von `ClassID` Werten, von denen jeder ein Argument der Funktion.</span><span class="sxs-lookup"><span data-stu-id="62c01-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="62c01-112">Der Wert der `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="62c01-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="62c01-113">[out] Ein Zeiger auf die `FunctionID` der angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="62c01-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c01-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62c01-114">Remarks</span></span>  
 <span data-ttu-id="62c01-115">Aufrufen der `GetFunctionFromTokenAndTypeArgs` Methode mit einer `mdMethodRef` Metadaten anstelle von einer `mdMethodDef` Metadatentoken kann unvorhersehbare Folgen haben.</span><span class="sxs-lookup"><span data-stu-id="62c01-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="62c01-116">Aufrufer sollten Auflösen der `mdMethodRef` auf eine `mdMethodDef` bei der Übergabe.</span><span class="sxs-lookup"><span data-stu-id="62c01-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="62c01-117">Wenn die Funktion nicht bereits geladen wurde, Aufrufen `GetFunctionFromTokenAndTypeArgs` führt dazu, dass Laden auftreten, die in vielen Kontexten einen gefährlichen Vorgang ist.</span><span class="sxs-lookup"><span data-stu-id="62c01-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="62c01-118">Beispielsweise kann beim Aufrufen dieser Methode beim Laden von Modulen oder Typen zu einer Endlosschleife führen wie die Laufzeitumgebung versucht, Ladevorgänge zirkulär durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="62c01-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="62c01-119">Verwenden Sie im Allgemeinen von `GetFunctionFromTokenAndTypeArgs` wird abgeraten.</span><span class="sxs-lookup"><span data-stu-id="62c01-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="62c01-120">Wenn der Profiler-Ereignisse für eine bestimmte Funktion interessiert sind, speichern sie die `ModuleID` und `mdMethodDef` dieser Funktion und Verwendung [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) zu überprüfen, ob eine angegebenen `FunctionID` ist der die gewünschte Funktion.</span><span class="sxs-lookup"><span data-stu-id="62c01-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c01-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62c01-121">Requirements</span></span>  
 <span data-ttu-id="62c01-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62c01-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c01-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62c01-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62c01-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62c01-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62c01-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c01-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c01-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62c01-126">See Also</span></span>  
 [<span data-ttu-id="62c01-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62c01-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="62c01-128">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62c01-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
