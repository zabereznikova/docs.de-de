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
ms.openlocfilehash: 5b6c0159b432d2a70f583357bbcf714b27399633
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447174"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="7b983-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs-Methode</span><span class="sxs-lookup"><span data-stu-id="7b983-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="7b983-103">Ruft den `ClassID` eines Typs unter Verwendung des angegebenen Metadatentokens und der `ClassID` Werte beliebiger Typargumente ab.</span><span class="sxs-lookup"><span data-stu-id="7b983-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b983-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b983-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b983-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b983-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="7b983-106">in Die ID des Moduls, in dem sich der Typ befindet.</span><span class="sxs-lookup"><span data-stu-id="7b983-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="7b983-107">in Ein `mdTypeDef` Metadatentoken, das auf den Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="7b983-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="7b983-108">in Die Anzahl der Typparameter für den angegebenen Typ.</span><span class="sxs-lookup"><span data-stu-id="7b983-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="7b983-109">Dieser Wert muss für nicht generische Typen NULL sein.</span><span class="sxs-lookup"><span data-stu-id="7b983-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="7b983-110">in Ein Array von `ClassID` Werten, von denen jeder ein Argument vom Typ ist.</span><span class="sxs-lookup"><span data-stu-id="7b983-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="7b983-111">Der Wert `typeArgs` kann NULL sein, wenn `cTypeArgs` auf NULL festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7b983-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="7b983-112">vorgenommen Ein Zeiger auf den `ClassID` des angegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="7b983-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b983-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b983-113">Remarks</span></span>  
 <span data-ttu-id="7b983-114">Wenn Sie die `GetClassFromTokenAndTypeArgs`-Methode mit einem `mdTypeRef` anstelle eines `mdTypeDef` Metadatentokens aufrufen, kann dies zu unvorhersehbaren Ergebnissen führen. Aufrufer sollten die `mdTypeRef` bei der Übergabe in eine `mdTypeDef` auflösen.</span><span class="sxs-lookup"><span data-stu-id="7b983-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="7b983-115">Wenn der Typ nicht bereits geladen ist, wird beim Aufrufen von `GetClassFromTokenAndTypeArgs` das Laden auslöst, was in vielen Kontexten eine gefährliche Operation ist.</span><span class="sxs-lookup"><span data-stu-id="7b983-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="7b983-116">Wenn Sie diese Methode z. b. beim Laden von Modulen oder anderen Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.</span><span class="sxs-lookup"><span data-stu-id="7b983-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="7b983-117">Im Allgemeinen wird die Verwendung von `GetClassFromTokenAndTypeArgs` davon abgeraten.</span><span class="sxs-lookup"><span data-stu-id="7b983-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="7b983-118">Wenn Profiler an Ereignissen für einen bestimmten Typ interessiert sind, sollten Sie die `ModuleID` und `mdTypeDef` dieses Typs speichern und [ICorProfilerInfo2:: GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) verwenden, um zu überprüfen, ob ein bestimmtes `ClassID` der gewünschte Typ ist.</span><span class="sxs-lookup"><span data-stu-id="7b983-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b983-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7b983-119">Requirements</span></span>  
 <span data-ttu-id="7b983-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b983-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b983-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b983-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b983-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b983-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b983-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b983-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b983-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b983-124">See also</span></span>

- [<span data-ttu-id="7b983-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b983-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="7b983-126">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b983-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
