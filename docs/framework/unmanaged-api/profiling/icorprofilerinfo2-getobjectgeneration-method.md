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
ms.openlocfilehash: b75de955e3b6857c9cc1b5411df4b0f262c4cb9a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862697"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>ICorProfilerInfo2::GetObjectGeneration-Methode
Ruft das Segment des Heaps ab, das das angegebene-Objekt enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a>Parameters  
 `objectId`  
 in Die ID des Objekts.  
  
 `range`  
 vorgenommen Ein Zeiger auf eine [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) -Struktur, die einen Bereich (d. h. einen Block) des Arbeitsspeichers in der Generierung beschreibt, die Garbage Collection wird. Dieser Bereich enthält das angegebene-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetObjectGeneration`-Methode kann von jedem Profiler-Rückruf aufgerufen werden, vorausgesetzt, dass Garbage Collection nicht ausgeführt wird. Das heißt, dass Sie von jedem Rückruf aufgerufen werden kann, außer denen, die zwischen [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: garbagecollectionbeendeten](icorprofilercallback2-garbagecollectionfinished-method.md)auftreten.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
