---
title: ICorProfilerInfo2::GetContextStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
ms.openlocfilehash: 067e5093cc3b141936eeec43e77e6e1a9475a8a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727119"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress-Methode

Ruft die Adresse für das angegebene Kontext statische Feld ab, das sich im Gültigkeitsbereich des angegebenen Kontexts befindet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parameter  

 `classId`  
 in Die ID der Klasse, die das angeforderte Kontext statische Feld enthält.  
  
 `fieldToken`  
 in Das Metadatentoken für das angeforderte Kontext statische Feld.  
  
 `contextId`  
 in Die ID des Kontexts, bei dem es sich um den Bereich für das angeforderte Kontext statische Feld handelt.  
  
 `ppAddress`  
 vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich im angegebenen Kontext befindet.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetContextStaticAddress` Methode kann eine der folgenden Methoden zurückgeben:  
  
- Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.  
  
- Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden. Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.  
  
 Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, `GetContextStaticAddress` gibt CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte mit rooting erstellt wurden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
