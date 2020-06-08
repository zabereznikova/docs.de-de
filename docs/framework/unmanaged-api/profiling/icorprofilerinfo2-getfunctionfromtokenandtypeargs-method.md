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
ms.openlocfilehash: 7f1276e1adeece086ca7b6791eb6e870faf4d010
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502872"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="c3f5b-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="c3f5b-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="c3f5b-103">Ruft den einer `FunctionID` Funktion mit dem angegebenen Metadatentoken, der Klasse und den `ClassID` Werten beliebiger Typargumente ab.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3f5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3f5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3f5b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3f5b-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c3f5b-106">in Die ID des Moduls, in dem sich die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="c3f5b-107">in Ein `mdMethodDef` Metadatentoken, das auf die Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="c3f5b-108">in Die ID der enthaltenden Klasse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c3f5b-109">in Die Anzahl der Typparameter für die angegebene Funktion.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="c3f5b-110">Dieser Wert muss für nicht generische Funktionen 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c3f5b-111">in Ein Array von- `ClassID` Werten, von denen jeder ein Argument der-Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="c3f5b-112">Der Wert von `typeArgs` kann NULL sein `cTypeArgs` , wenn auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="c3f5b-113">vorgenommen Ein Zeiger auf die `FunctionID` der angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3f5b-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c3f5b-114">Remarks</span></span>  
 <span data-ttu-id="c3f5b-115">Das Aufrufen der- `GetFunctionFromTokenAndTypeArgs` Methode mit `mdMethodRef` Metadaten anstelle eines `mdMethodDef` Metadatentokens kann zu unvorhersehbaren Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="c3f5b-116">Aufrufer sollten `mdMethodRef` bei der Übergabe in eine auflösen `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="c3f5b-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="c3f5b-117">Wenn die Funktion nicht bereits geladen ist, bewirkt das Aufrufen `GetFunctionFromTokenAndTypeArgs` von, dass geladen wird. Dies ist ein gefährlicher Vorgang in vielen Kontexten.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="c3f5b-118">Wenn Sie diese Methode beispielsweise beim Laden von Modulen oder Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="c3f5b-119">Im Allgemeinen wird von der Verwendung von abgeraten `GetFunctionFromTokenAndTypeArgs` .</span><span class="sxs-lookup"><span data-stu-id="c3f5b-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="c3f5b-120">Wenn Profiler an Ereignissen für eine bestimmte Funktion interessiert sind, sollten Sie die `ModuleID` und `mdMethodDef` dieser Funktion Speichern und [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) verwenden, um zu überprüfen, ob ein bestimmtes der `FunctionID` gewünschten Funktion entspricht.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3f5b-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3f5b-121">Requirements</span></span>  
 <span data-ttu-id="c3f5b-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3f5b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3f5b-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3f5b-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3f5b-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3f5b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3f5b-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3f5b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f5b-126">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-126">See also</span></span>

- [<span data-ttu-id="c3f5b-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3f5b-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c3f5b-128">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3f5b-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
