---
title: 'ICorProfilerInfo10:: isfrozenobject'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452187"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="04aae-102">ICorProfilerInfo10:: isfrozenobject-Methode</span><span class="sxs-lookup"><span data-stu-id="04aae-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="04aae-103">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="04aae-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="04aae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04aae-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="04aae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="04aae-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="04aae-106">\[in] das zu überprüfende-Objekt.</span><span class="sxs-lookup"><span data-stu-id="04aae-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="04aae-107">\[out] ein `BOOL`, der angibt, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="04aae-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="04aae-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="04aae-108">Requirements</span></span>

<span data-ttu-id="04aae-109">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="04aae-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="04aae-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04aae-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="04aae-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04aae-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="04aae-112">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04aae-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="04aae-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04aae-113">See also</span></span>

- [<span data-ttu-id="04aae-114">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04aae-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
