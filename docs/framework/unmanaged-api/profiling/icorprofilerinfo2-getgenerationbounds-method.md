---
title: ICorProfilerInfo2::GetGenerationBounds-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
ms.openlocfilehash: 2b9bf1a9f40764f6d0544bafb91f967905eb40c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703914"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a>ICorProfilerInfo2::GetGenerationBounds-Methode

Ruft die Arbeitsspeicherbereiche ab, die Segmente des Heaps sind, aus dem sich die verschiedenen Garbage Collection-Generationen zusammensetzen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `cObjectRanges`  
 [in] Die Anzahl der Elemente, die der Aufrufer dem `ranges`-Array zugeordnet hat.  
  
 `pcObjectRanges`  
 [out] Ein Zeiger auf eine ganze Zahl, die die Gesamtzahl der Bereiche angibt, von denen einige oder alle im `ranges`-Array zurückgegeben werden.  
  
 `ranges`  
 vorgenommen Ein Array von [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) Strukturen, von denen jedes einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation beschreibt, die Garbage Collection wird.  
  
## <a name="remarks"></a>Hinweise  

 Die `GetGenerationBounds`-Methode kann von jedem Profilerrückruf aufgerufen werden, solange die Garbage Collection nicht durchgeführt wird.

 Die meisten Generationenverschiebungen finden während der Garbage Collections statt. Generationen können zwischen Auflistungen anwachsen, verschieben sich im Allgemeinen jedoch nicht. Deshalb befinden sich die interessantesten Positionen zum Aufrufen von `GetGenerationBounds` in `ICorProfilerCallback2::GarbageCollectionStarted` und `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
 Während des Programmstarts werden einige Objekte in der Regel in den Generationen 3 und 0 von der Common Language Runtime (CLR) selbst zugeordnet. Daher enthalten diese Generationen zu dem Zeitpunkt, an dem der verwaltete Code die Ausführung startet, bereits Objekte. Die Generationen 1 und 2 sind normalerweise (bis auf vom Garbage Collector generierte Dummyobjekte) leer. (Die Größe der Dummyobjekte beträgt 12 Bytes in 32-Bit-Implementierungen der CLR; die Größe ist in 64-Bit-Implementierungen größer.) Es können auch Bereiche der Generation 2 angezeigt werden, die sich innerhalb von Modulen befinden, die vom Native Image Generator (NGen.exe) erstellt werden. In diesem Fall sind die Objekte in Generation 2 fixierte *Objekte*, die zugeordnet werden, wenn NGen.exe statt der Garbage Collector ausgeführt wird.  
  
 Diese Funktion verwendet vom Aufrufer reservierte Puffer.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
