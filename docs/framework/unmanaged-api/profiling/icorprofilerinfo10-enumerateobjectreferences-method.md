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
ms.openlocfilehash: ac193b6b78434245b8f11a4f627b4e1992feb8a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661278"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="365a3-102">ICorProfilerInfo10:: enumerateobjectreferences-Methode</span><span class="sxs-lookup"><span data-stu-id="365a3-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="365a3-103">Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="365a3-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="365a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="365a3-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a><span data-ttu-id="365a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="365a3-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="365a3-106">in Das Objekt, auf das Verweise aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="365a3-106">[in] The object to enumerate references on.</span></span>

`callback` \
<span data-ttu-id="365a3-107">in Die Funktion, die mit den verweisen für das-Objekt aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="365a3-107">[in] The function that will be called with the references for the object.</span></span>

`clientData` \
<span data-ttu-id="365a3-108">in Vom Profiler bereitgestellte Daten, die an `callback` die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="365a3-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="365a3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="365a3-109">Remarks</span></span>

<span data-ttu-id="365a3-110">Die `EnumerateObjectReferences` -Methode ähnelt [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), mit dem Unterschied, dass Sie die Verweise nach Bedarf für den Profiler durchläuft, anstatt ein Array zum Speichern der Verweise vorab zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="365a3-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="365a3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="365a3-111">Requirements</span></span>

<span data-ttu-id="365a3-112">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="365a3-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="365a3-113">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="365a3-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="365a3-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="365a3-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="365a3-115">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="365a3-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="365a3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="365a3-116">See also</span></span>

- [<span data-ttu-id="365a3-117">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="365a3-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
