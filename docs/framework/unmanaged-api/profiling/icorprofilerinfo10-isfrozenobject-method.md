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
ms.openlocfilehash: d212c06c7ddc9f22095c0b95f19fd1083482435c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661224"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="5d85e-102">ICorProfilerInfo10:: isfrozenobject-Methode</span><span class="sxs-lookup"><span data-stu-id="5d85e-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="5d85e-103">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="5d85e-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d85e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d85e-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="5d85e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d85e-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="5d85e-106">in Das zu überprüfende Objekt.</span><span class="sxs-lookup"><span data-stu-id="5d85e-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="5d85e-107">vorgenommen Ein `BOOL` Wert, der angibt, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="5d85e-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d85e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d85e-108">Requirements</span></span>

<span data-ttu-id="5d85e-109">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="5d85e-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="5d85e-110">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="5d85e-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5d85e-111">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d85e-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5d85e-112">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d85e-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5d85e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d85e-113">See also</span></span>

- [<span data-ttu-id="5d85e-114">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d85e-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
