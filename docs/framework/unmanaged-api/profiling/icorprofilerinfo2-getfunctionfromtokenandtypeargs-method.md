---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31fad9e82d0b93360f92676f6357c136ae60634a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771133"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="cf667-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="cf667-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="cf667-103">Ruft die `FunctionID` einer Funktion mit dem angegebenen Metadaten-Token, mit der Klasse, und `ClassID` Werte aller Typargumente.</span><span class="sxs-lookup"><span data-stu-id="cf667-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf667-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf667-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf667-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf667-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="cf667-106">[in] Die ID des Moduls, in dem die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="cf667-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="cf667-107">[in] Ein `mdMethodDef` Metadatentoken, das die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="cf667-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="cf667-108">[in] Die ID der enthaltenden Klasse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="cf667-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="cf667-109">[in] Die Anzahl der Typparameter für die angegebene Funktion.</span><span class="sxs-lookup"><span data-stu-id="cf667-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="cf667-110">Dieser Wert muss 0 (null) für nicht generische Funktionen sein.</span><span class="sxs-lookup"><span data-stu-id="cf667-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="cf667-111">[in] Ein Array von `ClassID` Werten, von denen jeder ein Argument der Funktion.</span><span class="sxs-lookup"><span data-stu-id="cf667-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="cf667-112">Der Wert des `typeArgs` kann NULL sein, wenn `cTypeArgs` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cf667-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="cf667-113">[out] Ein Zeiger auf die `FunctionID` der angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="cf667-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf667-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf667-114">Remarks</span></span>  
 <span data-ttu-id="cf667-115">Aufrufen der `GetFunctionFromTokenAndTypeArgs` -Methode mit einer `mdMethodRef` Metadaten anstelle von einer `mdMethodDef` Metadatentoken unvorhersehbare Ergebnisse haben.</span><span class="sxs-lookup"><span data-stu-id="cf667-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="cf667-116">Aufrufer sollten Auflösen der `mdMethodRef` auf eine `mdMethodDef` bei der Übergabe.</span><span class="sxs-lookup"><span data-stu-id="cf667-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="cf667-117">Wenn die Funktion nicht bereits geladen ist, wird beim Aufrufen `GetFunctionFromTokenAndTypeArgs` bewirkt, dass beim Laden auftreten, handelt es sich in vielen Kontexten einen gefährlichen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="cf667-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="cf667-118">Beispielsweise kann das Aufrufen dieser Methode während des Ladens von Modulen oder Typen zu einer Endlosschleife führen wie die Laufzeit versucht, die Ladevorgänge zirkulär durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cf667-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="cf667-119">Im Allgemeinen die Verwendung von `GetFunctionFromTokenAndTypeArgs` wird abgeraten.</span><span class="sxs-lookup"><span data-stu-id="cf667-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="cf667-120">Wenn der Profiler-Ereignisse für eine bestimmte Funktion interessiert sind, sollten sie speichern die `ModuleID` und `mdMethodDef` von dieser Funktion und Verwendung [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) um zu überprüfen, ob eine angegebene `FunctionID` ist mit der gewünschten Funktion.</span><span class="sxs-lookup"><span data-stu-id="cf667-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf667-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf667-121">Requirements</span></span>  
 <span data-ttu-id="cf667-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf667-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf667-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf667-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf667-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf667-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf667-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf667-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf667-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf667-126">See also</span></span>

- [<span data-ttu-id="cf667-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf667-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="cf667-128">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf667-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
