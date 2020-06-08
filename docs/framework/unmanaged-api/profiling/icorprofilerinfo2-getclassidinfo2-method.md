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
ms.openlocfilehash: a33e51969dc0579d976f08470ebc6e2bcca04dd7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497165"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="1d687-102">ICorProfilerInfo2::GetClassIDInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="1d687-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="1d687-103">Ruft das übergeordnete Modul und das Metadatentoken für die offene generische Definition der angegebenen Klasse, die `ClassID` der übergeordneten Klasse und die `ClassID` für jedes Typargument (sofern vorhanden) der Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="1d687-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d687-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d687-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1d687-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d687-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1d687-106">[in] Die ID der Klasse, für die Informationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1d687-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="1d687-107">vorgenommen Ein Zeiger auf die ID des übergeordneten Moduls für die offene generische Definition der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="1d687-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="1d687-108">vorgenommen Zeiger auf das Metadatentoken für die offene generische Definition der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="1d687-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="1d687-109">[out] Der Zeiger auf die ID der übergeordneten Klasse.</span><span class="sxs-lookup"><span data-stu-id="1d687-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="1d687-110">[in] Die Größe des `typeArgs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="1d687-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="1d687-111">[out] Der Zeiger auf die Gesamtzahl der verfügbaren Elemente.</span><span class="sxs-lookup"><span data-stu-id="1d687-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="1d687-112">[out] Ein Array von `ClassID`-Werten, von denen jedes die ID eines Typarguments der Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="1d687-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="1d687-113">Wenn die Methode zurückkehrt, enthält `typeArgs` einige verfügbare oder alle verfügbaren `ClassID` Werte.</span><span class="sxs-lookup"><span data-stu-id="1d687-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d687-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1d687-114">Remarks</span></span>  
 <span data-ttu-id="1d687-115">Die- `GetClassIDInfo2` Methode ähnelt der [ICorProfilerInfo:: GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) -Methode, `GetClassIDInfo2` erhält aber zusätzliche Informationen über einen generischen Typ.</span><span class="sxs-lookup"><span data-stu-id="1d687-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="1d687-116">Der Profiler-Code kann [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) aufrufen, um eine [Metadatenschnittstelle](../metadata/index.md) für ein bestimmtes Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1d687-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="1d687-117">Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d687-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="1d687-118">Nachdem `GetClassIDInfo2` zurückgegeben wurde, müssen Sie sicherstellen, dass der `typeArgs`-Puffer groß genug war, um alle `ClassID`-Werte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1d687-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="1d687-119">Vergleichen Sie zu diesem Zweck den Wert, auf den `pcNumTypeArgs` verweist, mit dem Wert des Parameters `cNumTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="1d687-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="1d687-120">Wenn `pcNumTypeArgs` auf einen Wert verweist, der größer als `cNumTypeArgs` ist, weisen Sie einen größeren `typeArgs`-Puffer zu, aktualisieren Sie `cNumTypeArgs` mit der neuen Größe, und rufen Sie `GetClassIDInfo2` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="1d687-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="1d687-121">Alternativ können Sie zuerst `GetClassIDInfo2` mit einem `typeArgs`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="1d687-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="1d687-122">Sie können die `typeArgs`Puffergröße dann auf den Wert festlegen, der von `pcNumTypeArgs` zurückgegeben wurde, und `GetClassIDInfo2` dann erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1d687-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d687-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1d687-123">Requirements</span></span>  
 <span data-ttu-id="1d687-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d687-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d687-125">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d687-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d687-126">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d687-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d687-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d687-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d687-128">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1d687-128">See also</span></span>

- [<span data-ttu-id="1d687-129">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d687-129">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1d687-130">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d687-130">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="1d687-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1d687-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1d687-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="1d687-132">Profiling</span></span>](index.md)
