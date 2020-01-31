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
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863308"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="cfb98-102">ICorProfilerInfo10:: enumerateobjectreferences-Methode</span><span class="sxs-lookup"><span data-stu-id="cfb98-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="cfb98-103">Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="cfb98-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="cfb98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfb98-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="cfb98-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="cfb98-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="cfb98-106">\[in] das-Objekt, für das Verweise aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cfb98-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="cfb98-107">\[in] die Funktion, die mit den verweisen für das-Objekt aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cfb98-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="cfb98-108">\[in] vom Profiler bereitgestellte Daten, die an die `callback`-Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cfb98-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfb98-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfb98-109">Remarks</span></span>

<span data-ttu-id="cfb98-110">Die `EnumerateObjectReferences`-Methode ähnelt [ObjectReferences](icorprofilercallback-objectreferences-method.md), mit dem Unterschied, dass Sie die Verweise nach Bedarf für den Profiler durchläuft, anstatt ein Array zum Speichern der Verweise vorab zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="cfb98-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="cfb98-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfb98-111">Requirements</span></span>

<span data-ttu-id="cfb98-112">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="cfb98-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="cfb98-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cfb98-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="cfb98-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfb98-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="cfb98-115">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb98-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cfb98-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfb98-116">See also</span></span>

- [<span data-ttu-id="cfb98-117">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfb98-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
