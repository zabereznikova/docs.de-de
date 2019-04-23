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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dac7e38d1e767a3edeef932a0c0916daffe24b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092031"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="26451-102">ICorProfilerInfo2::GetBoxClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="26451-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="26451-103">Ruft Informationen über die auf dem sich der angegebene Werttyp befindet, wenn sie mittels Boxing konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="26451-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26451-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26451-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26451-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="26451-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="26451-106">[in] Die ID der Klasse, die den Werttyp beschreibt, der mittels Boxing konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="26451-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="26451-107">[out] Eine ganze Zahl, die der Offset relativ zu der geschachteltes Objekt-ID-Zeiger, der den Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="26451-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26451-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26451-108">Remarks</span></span>  
 <span data-ttu-id="26451-109">Die `pBufferOffset` Wert ist der Speicherort des Werttyps innerhalb eines Felds.</span><span class="sxs-lookup"><span data-stu-id="26451-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="26451-110">Nach dem `pBufferOffset` wird angewendet, in ein geschachteltes Objekt Klassenlayout des Werttyps verwendet werden kann, um den Wert des Objekts zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="26451-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26451-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26451-111">Requirements</span></span>  
 <span data-ttu-id="26451-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26451-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26451-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26451-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26451-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26451-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26451-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26451-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26451-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26451-116">See also</span></span>

- [<span data-ttu-id="26451-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26451-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="26451-118">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26451-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
