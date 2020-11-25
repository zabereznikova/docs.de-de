---
title: ICorProfilerInfo2::GetClassLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
ms.openlocfilehash: a2bac05e7471a0df8d624bf5dfbe2aa58c25cf4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727171"
---
# <a name="icorprofilerinfo2getclasslayout-method"></a><span data-ttu-id="6f5c1-102">ICorProfilerInfo2::GetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="6f5c1-102">ICorProfilerInfo2::GetClassLayout Method</span></span>

<span data-ttu-id="6f5c1-103">Ruft aus dem Arbeitsspeicher Informationen über das Layout der Felder ab, die durch die angegebene Klasse definiert sind .</span><span class="sxs-lookup"><span data-stu-id="6f5c1-103">Gets information about the layout, in memory, of the fields defined by the specified class.</span></span> <span data-ttu-id="6f5c1-104">Das heißt, diese Methode ruft die Offsets der Felder der Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-104">That is, this method gets the offsets of the class's fields.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5c1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f5c1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f5c1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f5c1-106">Parameters</span></span>  

 `classID`  
 <span data-ttu-id="6f5c1-107">[in] Die ID der Klasse, für das Layout abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-107">[in] The ID of the class for which the layout will be retrieved.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="6f5c1-108">[in, out] Ein Array von [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) Strukturen, die jeweils die Token und Offsets der Klassen Felder enthalten.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-108">[in, out] An array of [COR_FIELD_OFFSET](../metadata/cor-field-offset-structure.md) structures, each of which contains the tokens and offsets of the class's fields.</span></span>  
  
 `cFieldOffset`  
 <span data-ttu-id="6f5c1-109">[in] Die Größe des `rFieldOffset`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-109">[in] The size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="6f5c1-110">[out] Ein Zeiger auf die Gesamtzahl der verfügbaren Elemente.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-110">[out] A pointer to the total number of available elements.</span></span> <span data-ttu-id="6f5c1-111">Wenn `cFieldOffset` gleich 0 ist, gibt dieser Wert gibt die Anzahl von benötigten Elementen an.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-111">If `cFieldOffset` is 0, this value indicates the number of elements needed.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="6f5c1-112">[out] Ein Zeiger auf einen Speicherort, der die Größe der Klasse in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-112">[out] A pointer to a location that contains the size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f5c1-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f5c1-113">Remarks</span></span>  

 <span data-ttu-id="6f5c1-114">Die `GetClassLayout`-Methode gibt nur die von der Klasse selbst definierten Felder zurück.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-114">The `GetClassLayout` method returns only the fields defined by the class itself.</span></span> <span data-ttu-id="6f5c1-115">Wenn die übergeordnete Klasse der Klasse ebenfalls Felder definiert hat, muss der Profiler die `GetClassLayout`-Methode für die übergeordnete Klasse aufrufen, um diese Felder abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-115">If the class's parent class has defined fields as well, the profiler must call `GetClassLayout` on the parent class to obtain those fields.</span></span>  
  
 <span data-ttu-id="6f5c1-116">Wenn Sie `GetClassLayout` mit Zeichenfolgenklassen verwenden, schlägt die Methode mit dem Fehlercode E_INVALIDARG fehl.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-116">If you use `GetClassLayout` with string classes, the method will fail with error code E_INVALIDARG.</span></span> <span data-ttu-id="6f5c1-117">Verwenden Sie [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) , um Informationen über das Layout einer Zeichenfolge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-117">Use [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) to get information about the layout of a string.</span></span> <span data-ttu-id="6f5c1-118">Die `GetClassLayout`-Methode schlägt auch fehl, wenn sie mit einer Arrayklasse aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-118">`GetClassLayout` will also fail when called with an array class.</span></span>  
  
 <span data-ttu-id="6f5c1-119">Nachdem `GetClassLayout` abgeschlossen ist, müssen Sie sicherstellen, dass der `rFieldOffset`-Puffer groß genug war, um alle verfügbaren `COR_FIELD_OFFSET`-Strukturen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-119">After `GetClassLayout` returns, you must verify that the `rFieldOffset` buffer was large enough to contain all the available `COR_FIELD_OFFSET` structures.</span></span> <span data-ttu-id="6f5c1-120">Vergleichen Sie hierzu den Wert, auf den `pcFieldOffset` verweist, mit der Größe von `rFieldOffset` dividiert durch die Größe einer `COR_FIELD_OFFSET`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-120">To do this, compare the value that `pcFieldOffset` points to with the size of `rFieldOffset` divided by the size of a `COR_FIELD_OFFSET` structure.</span></span> <span data-ttu-id="6f5c1-121">Wenn `rFieldOffset` nicht groß genug ist, weisen Sie einen größeren `rFieldOffset`-Puffer zu, aktualisieren Sie `cFieldOffset` mit der neuen Größe, und rufen Sie `GetClassLayout` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-121">If `rFieldOffset` is not large enough, allocate a larger `rFieldOffset` buffer, update `cFieldOffset` with the new, larger size, and call `GetClassLayout` again.</span></span>  
  
 <span data-ttu-id="6f5c1-122">Alternativ können Sie zuerst `GetClassLayout` mit einem `rFieldOffset`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-122">Alternatively, you can first call `GetClassLayout` with a zero-length `rFieldOffset` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="6f5c1-123">Sie können die Puffergröße dann auf den Wert festlegen, der von `pcFieldOffset` zurückgegeben wurde, und `GetClassLayout` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6f5c1-123">You can then set the buffer size to the value returned in `pcFieldOffset` and call `GetClassLayout` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5c1-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f5c1-124">Requirements</span></span>  

 <span data-ttu-id="6f5c1-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5c1-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5c1-126">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f5c1-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f5c1-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f5c1-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f5c1-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5c1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5c1-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f5c1-129">See also</span></span>

- [<span data-ttu-id="6f5c1-130">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f5c1-130">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6f5c1-131">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f5c1-131">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="6f5c1-132">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f5c1-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6f5c1-133">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="6f5c1-133">Profiling</span></span>](index.md)
