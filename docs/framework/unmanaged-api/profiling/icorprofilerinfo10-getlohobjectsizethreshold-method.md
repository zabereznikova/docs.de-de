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
ms.openlocfilehash: 280f0a401f87f81e1ef9d4a2c85c06599442b5ec
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543945"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="6800e-102">ICorProfilerInfo10:: getlohobjectsizethreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="6800e-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="6800e-103">Ruft den Wert des konfigurierten Heap-Schwellenwerts (Large Object Heap) ab.</span><span class="sxs-lookup"><span data-stu-id="6800e-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="6800e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6800e-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="6800e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6800e-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="6800e-106">\[out] der Schwellenwert für große Objekt Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="6800e-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="6800e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6800e-107">Remarks</span></span>

<span data-ttu-id="6800e-108">Objekte, die größer sind als der Schwellenwert für den großen Objekt Heap, werden auf dem großen Objekt Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6800e-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="6800e-109">Ab .net Core 3,0 ist der Schwellenwert für den großen Objekt Heap konfigurierbar, `pThreshold` der die Schwellenwert Größe für den aktiven großen Objekt Heap in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="6800e-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="6800e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6800e-110">Requirements</span></span>

<span data-ttu-id="6800e-111">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="6800e-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="6800e-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6800e-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6800e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6800e-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6800e-114">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6800e-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6800e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6800e-115">See also</span></span>

- [<span data-ttu-id="6800e-116">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6800e-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
