---
title: ICorProfilerInfo2::GetBoxClassLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 500cf74c320438fc1b78f0aac737b418716e1a11
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862827"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="3c31f-102">ICorProfilerInfo2::GetBoxClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="3c31f-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="3c31f-103">Ruft Informationen darüber ab, wo sich der angegebene Werttyp befindet, wenn er gekapselt wird.</span><span class="sxs-lookup"><span data-stu-id="3c31f-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c31f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c31f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c31f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3c31f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3c31f-106">in Die ID der Klasse, die den zu boachtelten Werttyp beschreibt.</span><span class="sxs-lookup"><span data-stu-id="3c31f-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="3c31f-107">vorgenommen Eine ganze Zahl, die den Offset des Werttyps relativ zum Objekt-ID-Zeiger des Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="3c31f-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c31f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c31f-108">Remarks</span></span>  
 <span data-ttu-id="3c31f-109">Der `pBufferOffset` Wert ist der Speicherort des Werttyps in einem Feld.</span><span class="sxs-lookup"><span data-stu-id="3c31f-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="3c31f-110">Nachdem `pBufferOffset` auf ein geachteltes Objekt angewendet wurde, kann das Klassen Layout des Werttyps verwendet werden, um den Wert des Objekts zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="3c31f-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c31f-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c31f-111">Requirements</span></span>  
 <span data-ttu-id="3c31f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c31f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c31f-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c31f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c31f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c31f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c31f-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c31f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c31f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c31f-116">See also</span></span>

- [<span data-ttu-id="3c31f-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c31f-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3c31f-118">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c31f-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
