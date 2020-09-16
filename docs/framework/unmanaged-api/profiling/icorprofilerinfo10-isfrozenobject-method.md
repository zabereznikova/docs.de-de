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
ms.openlocfilehash: 3755260b885768de6b5b2d6342c0ad590a95caff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548669"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="7c72c-102">ICorProfilerInfo10:: isfrozenobject-Methode</span><span class="sxs-lookup"><span data-stu-id="7c72c-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="7c72c-103">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="7c72c-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c72c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c72c-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="7c72c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c72c-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="7c72c-106">\[in] das zu überprüfende-Objekt.</span><span class="sxs-lookup"><span data-stu-id="7c72c-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="7c72c-107">\[out] ein-Wert, `BOOL` der angibt, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="7c72c-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c72c-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c72c-108">Requirements</span></span>

<span data-ttu-id="7c72c-109">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="7c72c-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="7c72c-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c72c-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="7c72c-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c72c-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="7c72c-112">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c72c-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7c72c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c72c-113">See also</span></span>

- [<span data-ttu-id="7c72c-114">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c72c-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
