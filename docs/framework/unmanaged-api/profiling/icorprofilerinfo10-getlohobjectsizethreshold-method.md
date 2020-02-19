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
ms.openlocfilehash: 7a0f6f6bea5bc919ebfe9c9acc3b02a31eaa7cd0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452213"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="1d4ed-102">ICorProfilerInfo10:: getlohobjectsizethreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="1d4ed-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="1d4ed-103">Ruft den Wert des konfigurierten Heap-Schwellenwerts (Large Object Heap) ab.</span><span class="sxs-lookup"><span data-stu-id="1d4ed-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d4ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d4ed-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="1d4ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d4ed-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="1d4ed-106">\[out] der Schwellenwert für große Objekt Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="1d4ed-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d4ed-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d4ed-107">Remarks</span></span>

<span data-ttu-id="1d4ed-108">Objekte, die größer sind als der Schwellenwert für den großen Objekt Heap, werden auf dem großen Objekt Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1d4ed-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="1d4ed-109">Ab .net Core 3,0 ist der Schwellenwert für den großen Objekt Heap konfigurierbar, `pThreshold` den Schwellenwert für den aktiven Heap für große Objekte in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="1d4ed-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d4ed-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1d4ed-110">Requirements</span></span>

<span data-ttu-id="1d4ed-111">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="1d4ed-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="1d4ed-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d4ed-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1d4ed-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d4ed-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1d4ed-114">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d4ed-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1d4ed-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d4ed-115">See also</span></span>

- [<span data-ttu-id="1d4ed-116">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d4ed-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
