---
title: 'ICorProfilerInfo10:: enumerateobjectreferences'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a276ecfe65ed9752f39ed68a36e8e17a24255508
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558315"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="b8b45-102">ICorProfilerInfo10:: enumerateobjectreferences-Methode</span><span class="sxs-lookup"><span data-stu-id="b8b45-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="b8b45-103">Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="b8b45-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="b8b45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8b45-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="b8b45-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8b45-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="b8b45-106">\[in] das-Objekt, für das Verweise aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b8b45-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="b8b45-107">\[in] die Funktion, die mit den verweisen für das-Objekt aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b8b45-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="b8b45-108">\[in] vom Profiler bereitgestellte Daten, die an die Funktion übergeben werden `callback` .</span><span class="sxs-lookup"><span data-stu-id="b8b45-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8b45-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8b45-109">Remarks</span></span>

<span data-ttu-id="b8b45-110">Die- `EnumerateObjectReferences` Methode ähnelt [ObjectReferences](icorprofilercallback-objectreferences-method.md), mit dem Unterschied, dass Sie die Verweise nach Bedarf für den Profiler durchläuft, anstatt ein Array zum Speichern der Verweise vorab zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b8b45-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8b45-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8b45-111">Requirements</span></span>

<span data-ttu-id="b8b45-112">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="b8b45-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="b8b45-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8b45-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b8b45-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8b45-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b8b45-115">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8b45-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b8b45-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8b45-116">See also</span></span>

- [<span data-ttu-id="b8b45-117">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8b45-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
