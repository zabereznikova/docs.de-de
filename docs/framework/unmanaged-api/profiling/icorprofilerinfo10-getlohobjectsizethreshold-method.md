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
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661244"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="9b168-102">ICorProfilerInfo10:: getlohobjectsizethreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="9b168-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="9b168-103">Ruft den Wert des konfigurierten Heap-Schwellenwerts (Large Object Heap) ab.</span><span class="sxs-lookup"><span data-stu-id="9b168-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="9b168-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b168-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="9b168-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b168-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="9b168-106">vorgenommen Der Schwellenwert für große Objekt Heaps in Bytes.</span><span class="sxs-lookup"><span data-stu-id="9b168-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b168-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b168-107">Remarks</span></span>

<span data-ttu-id="9b168-108">Objekte, die größer sind als der Schwellenwert für den großen Objekt Heap, werden auf dem großen Objekt Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9b168-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="9b168-109">Ab .net Core 3,0 ist der Schwellenwert für den großen Objekt Heap `pThreshold` konfigurierbar, der die Schwellenwert Größe für den aktiven großen Objekt Heap in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="9b168-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b168-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b168-110">Requirements</span></span>

<span data-ttu-id="9b168-111">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="9b168-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="9b168-112">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="9b168-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="9b168-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b168-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9b168-114">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b168-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9b168-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b168-115">See also</span></span>

- [<span data-ttu-id="9b168-116">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b168-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
