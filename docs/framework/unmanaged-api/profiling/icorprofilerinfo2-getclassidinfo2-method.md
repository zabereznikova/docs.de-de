---
title: ICorProfilerInfo2::GetClassIDInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 8ce02b8b44074bed2da9e302f95a67a528601bf8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433436"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="dc700-102">ICorProfilerInfo2::GetClassIDInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="dc700-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="dc700-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span><span class="sxs-lookup"><span data-stu-id="dc700-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc700-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc700-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc700-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc700-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="dc700-106">[in] Die ID der Klasse, für die Informationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc700-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="dc700-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span><span class="sxs-lookup"><span data-stu-id="dc700-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="dc700-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span><span class="sxs-lookup"><span data-stu-id="dc700-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="dc700-109">[out] Der Zeiger auf die ID der übergeordneten Klasse.</span><span class="sxs-lookup"><span data-stu-id="dc700-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="dc700-110">[in] Die Größe des `typeArgs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="dc700-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="dc700-111">[out] Der Zeiger auf die Gesamtzahl der verfügbaren Elemente.</span><span class="sxs-lookup"><span data-stu-id="dc700-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="dc700-112">[out] Ein Array von `ClassID`-Werten, von denen jedes die ID eines Typarguments der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc700-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="dc700-113">Wenn die Methode zurückkehrt, enthält `typeArgs` einige verfügbare oder alle verfügbaren `ClassID` Werte.</span><span class="sxs-lookup"><span data-stu-id="dc700-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc700-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc700-114">Remarks</span></span>  
 <span data-ttu-id="dc700-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span><span class="sxs-lookup"><span data-stu-id="dc700-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="dc700-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span><span class="sxs-lookup"><span data-stu-id="dc700-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="dc700-117">Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc700-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="dc700-118">Nachdem `GetClassIDInfo2` zurückgegeben wurde, müssen Sie sicherstellen, dass der `typeArgs`-Puffer groß genug war, um alle `ClassID`-Werte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="dc700-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="dc700-119">Vergleichen Sie zu diesem Zweck den Wert, auf den `pcNumTypeArgs` verweist, mit dem Wert des Parameters `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="dc700-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="dc700-120">Wenn `pcNumTypeArgs` auf einen Wert verweist, der größer als `cNumTypeArgs` ist, weisen Sie einen größeren `typeArgs`-Puffer zu, aktualisieren Sie `cNumTypeArgs` mit der neuen Größe, und rufen Sie `GetClassIDInfo2` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="dc700-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="dc700-121">Alternativ können Sie zuerst `GetClassIDInfo2` mit einem `typeArgs`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="dc700-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="dc700-122">Sie können die `typeArgs`Puffergröße dann auf den Wert festlegen, der von `pcNumTypeArgs` zurückgegeben wurde, und `GetClassIDInfo2` dann erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="dc700-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc700-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc700-123">Requirements</span></span>  
 <span data-ttu-id="dc700-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc700-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc700-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc700-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc700-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc700-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc700-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc700-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc700-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc700-128">See also</span></span>

- [<span data-ttu-id="dc700-129">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc700-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="dc700-130">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc700-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="dc700-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="dc700-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="dc700-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="dc700-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
