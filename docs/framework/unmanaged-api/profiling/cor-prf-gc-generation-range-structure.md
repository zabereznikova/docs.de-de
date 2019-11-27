---
title: COR_PRF_GC_GENERATION_RANGE-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: 0bdb8cd02e0beb69e3ec594b0aadd741a5f0d924
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428334"
---
# <a name="cor_prf_gc_generation_range-structure"></a>COR_PRF_GC_GENERATION_RANGE-Struktur
Beschreibt einen Bereich (d. h. einen Block) des Speichers, der einer Garbage Collection unterzogen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`generation`|Ein Wert der [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) -Enumeration, die die Generierung angibt, zu der der Speicherblock gehört.|  
|`rangeStart`|Die ID eines Objekts, das die Startposition des Speicherblocks angibt.|  
|`rangeLength`|Ein Zeiger auf eine ganze Zahl, die die Größe des verwendeten Teils des Speicherblocks angibt (d. h. die Menge an Arbeitsspeicher, die im Block verwendet wird).|  
|`rangeLengthReserved`|Ein Zeiger auf eine ganze Zahl, die die Größe des Speicherblocks angibt (d. h. die Menge an Arbeitsspeicher, die für den Block reserviert ist).|  
  
## <a name="remarks"></a>Hinweise  
 Der `rangeLength` Wert ist garantiert nur dann genau, wenn [ICorProfilerInfo2:: GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) oder [ICorProfilerInfo2:: getobjectgene Ration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), die beide die `COR_PRF_GC_GENERATION_RANGE` Struktur verwenden, von der [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) -Methode oder der [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) -Methode aufgerufen wird.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsstrukturen](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
