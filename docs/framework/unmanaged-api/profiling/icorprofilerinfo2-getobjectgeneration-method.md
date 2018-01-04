---
title: ICorProfilerInfo2::GetObjectGeneration-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetObjectGeneration
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a28b5e031ae39be39cc00740043b86ef2a9854
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>ICorProfilerInfo2::GetObjectGeneration-Methode
Ruft das Segment des Heaps, die das angegebene Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts.  
  
 `range`  
 [out] Ein Zeiger auf eine [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) -Struktur, die einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation beschreibt, die Garbagecollection unterzogen wird. Dieser Bereich enthält das angegebene Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetObjectGeneration` Methode kann von jedem Profilerrückruf aufgerufen werden, vorausgesetzt, dass die Garbagecollection nicht ausgeführt wird. D. h. möglicherweise von einem beliebigen Rückruf mit Ausnahme von those, die occur an zwischen aufgerufen werden [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
