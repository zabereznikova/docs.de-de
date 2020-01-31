---
title: 'ICorProfilerInfo10:: getlohobjectsizethreshold'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 95473a8ce8d5fd7540228ecd9767448e51b5b326
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868983"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="89772-102">ICorProfilerInfo10:: getlohobjectsizethreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="89772-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="89772-103">Ruft den Wert des konfigurierten Heap-Schwellenwerts (Large Object Heap) ab.</span><span class="sxs-lookup"><span data-stu-id="89772-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="89772-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89772-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="89772-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="89772-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="89772-106">\[out] der Schwellenwert für große Objekt Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="89772-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="89772-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89772-107">Remarks</span></span>

<span data-ttu-id="89772-108">Objekte, die größer sind als der Schwellenwert für den großen Objekt Heap, werden auf dem großen Objekt Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="89772-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="89772-109">Ab .net Core 3,0 ist der Schwellenwert für den großen Objekt Heap konfigurierbar, `pThreshold` den Schwellenwert für den aktiven Heap für große Objekte in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="89772-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="89772-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89772-110">Requirements</span></span>

<span data-ttu-id="89772-111">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="89772-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="89772-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89772-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="89772-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89772-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="89772-114">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89772-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="89772-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89772-115">See also</span></span>

- [<span data-ttu-id="89772-116">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89772-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
