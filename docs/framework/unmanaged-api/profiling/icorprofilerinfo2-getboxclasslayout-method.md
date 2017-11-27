---
title: ICorProfilerInfo2::GetBoxClassLayout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetBoxClassLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c11013781a4fc8f627dac97894ff9ef02bfda51c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="2f7c4-102">ICorProfilerInfo2::GetBoxClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="2f7c4-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="2f7c4-103">Ruft Informationen darüber, in denen der angegebene Werttyp befindet, wenn er mittels Boxing konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f7c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f7c4-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f7c4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f7c4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2f7c4-106">[in] Die ID der Klasse, die den Werttyp beschreibt, der mittels Boxing konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="2f7c4-107">[out] Eine ganze Zahl, die der Offset relativ zu den geschachteltes Objekt-ID-Zeiger des Werttyps ist.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f7c4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f7c4-108">Remarks</span></span>  
 <span data-ttu-id="2f7c4-109">Die `pBufferOffset` Wert ist der Speicherort des Werttyps innerhalb eines Felds.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="2f7c4-110">Nach dem `pBufferOffset` wird angewendet, in ein geschachteltes Objekt den Werttyp Klassenlayout verwendet werden kann, um den Wert des Objekts zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="2f7c4-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f7c4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f7c4-111">Requirements</span></span>  
 <span data-ttu-id="2f7c4-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f7c4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f7c4-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f7c4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f7c4-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f7c4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f7c4-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f7c4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7c4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f7c4-116">See Also</span></span>  
 [<span data-ttu-id="2f7c4-117">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f7c4-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2f7c4-118">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f7c4-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
