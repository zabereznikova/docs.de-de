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
ms.openlocfilehash: 62aad8339b34a4831211a45bd645906d73393d25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727145"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="935e0-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="935e0-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>

<span data-ttu-id="935e0-103">Ruft die `ClassID` eines Typs unter Verwendung des angegebenen Metadatentokens und der `ClassID` Werte von Typargumenten ab.</span><span class="sxs-lookup"><span data-stu-id="935e0-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="935e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="935e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="935e0-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="935e0-106">in Die ID des Moduls, in dem sich der Typ befindet.</span><span class="sxs-lookup"><span data-stu-id="935e0-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="935e0-107">in Ein `mdTypeDef` Metadatentoken, das auf den Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="935e0-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="935e0-108">in Die Anzahl der Typparameter für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="935e0-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="935e0-109">Dieser Wert muss für nicht generische Typen NULL sein.</span><span class="sxs-lookup"><span data-stu-id="935e0-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="935e0-110">in Ein Array von- `ClassID` Werten, von denen jeder ein Argument vom Typ ist.</span><span class="sxs-lookup"><span data-stu-id="935e0-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="935e0-111">Der Wert von `typeArgs` kann NULL sein `cTypeArgs` , wenn auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="935e0-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="935e0-112">vorgenommen Ein Zeiger auf den `ClassID` des angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="935e0-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="935e0-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="935e0-113">Remarks</span></span>  

 <span data-ttu-id="935e0-114">Das Aufrufen der- `GetClassFromTokenAndTypeArgs` Methode mit einem anstelle eines metadatentyps `mdTypeRef` `mdTypeDef` kann zu unvorhersehbaren Ergebnissen führen. Aufrufer sollten `mdTypeRef` bei der Übergabe in eine auflösen `mdTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="935e0-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="935e0-115">Wenn der Typ nicht bereits geladen ist, wird beim Aufrufen von das `GetClassFromTokenAndTypeArgs` Laden von auslöst, was in vielen Kontexten eine gefährliche Operation ist.</span><span class="sxs-lookup"><span data-stu-id="935e0-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="935e0-116">Wenn Sie diese Methode z. b. beim Laden von Modulen oder anderen Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.</span><span class="sxs-lookup"><span data-stu-id="935e0-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="935e0-117">Im Allgemeinen wird von der Verwendung von abgeraten `GetClassFromTokenAndTypeArgs` .</span><span class="sxs-lookup"><span data-stu-id="935e0-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="935e0-118">Wenn Profiler an Ereignissen für einen bestimmten Typ interessiert sind, sollten Sie das `ModuleID` und `mdTypeDef` dieses Typs speichern und [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) verwenden, um zu überprüfen, ob ein angegebenes der `ClassID` gewünschten Art ist.</span><span class="sxs-lookup"><span data-stu-id="935e0-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="935e0-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="935e0-119">Requirements</span></span>  

 <span data-ttu-id="935e0-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="935e0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935e0-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="935e0-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="935e0-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="935e0-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="935e0-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="935e0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935e0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="935e0-124">See also</span></span>

- [<span data-ttu-id="935e0-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="935e0-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="935e0-126">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="935e0-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
