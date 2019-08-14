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
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973990"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="037ba-102">ICorProfilerInfo10:: isfrozenobject-Methode</span><span class="sxs-lookup"><span data-stu-id="037ba-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>
  
 <span data-ttu-id="037ba-103">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="037ba-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="037ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="037ba-104">Syntax</span></span>  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a><span data-ttu-id="037ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="037ba-105">Parameters</span></span>  
 
 `objectId` \
 <span data-ttu-id="037ba-106">in Das zu überprüfende Objekt.</span><span class="sxs-lookup"><span data-stu-id="037ba-106">[in] The object to examine.</span></span>

 `pbFrozen` \
 <span data-ttu-id="037ba-107">vorgenommen Ein `BOOL` Wert, der angibt, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="037ba-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="037ba-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="037ba-108">Requirements</span></span>  
 <span data-ttu-id="037ba-109">**Formen** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="037ba-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="037ba-110">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="037ba-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="037ba-111">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="037ba-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="037ba-112">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="037ba-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="037ba-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="037ba-113">See also</span></span>
- [<span data-ttu-id="037ba-114">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="037ba-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

