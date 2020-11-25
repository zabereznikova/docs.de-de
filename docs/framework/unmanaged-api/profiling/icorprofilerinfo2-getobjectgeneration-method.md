---
title: ICorProfilerInfo2::GetObjectGeneration-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
ms.openlocfilehash: 4ba404692bef84c0522a799c61f07eac341eaab4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703846"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>ICorProfilerInfo2::GetObjectGeneration-Methode

Ruft das Segment des Heaps ab, das das angegebene-Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a>Parameter  

 `objectId`  
 in Die ID des Objekts.  
  
 `range`  
 vorgenommen Ein Zeiger auf eine [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) -Struktur, die einen Bereich (d. h. einen Block) des Arbeitsspeichers in der Generierung beschreibt, die Garbage Collection wird. Dieser Bereich enthält das angegebene-Objekt.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetObjectGeneration` Methode kann von jedem Profiler-Rückruf aufgerufen werden, sofern Garbage Collection nicht ausgeführt wird. Das heißt, dass Sie von jedem Rückruf aufgerufen werden kann, außer denen, die zwischen [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: garbagecollectionbeendeten](icorprofilercallback2-garbagecollectionfinished-method.md)auftreten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
