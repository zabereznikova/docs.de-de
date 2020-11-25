---
title: ICorProfilerInfo3::GetThreadStaticAddress2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: d8f2788d63f27aac30cf239b410eecea31f09212
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697882"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>ICorProfilerInfo3::GetThreadStaticAddress2-Methode

Ruft die Adresse des angegebenen threadstatischen Felds im Bereich des angegebenen Threads und der Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parameter  

 `classId`  
 in Die ID der Klasse, die das angeforderte Thread statische Feld enthält.  
  
 `fieldToken`  
 in Das Metadatentoken für das angeforderte Thread statische Feld.  
  
 `appDomainId`  
 [in] Die ID der Anwendungsdomäne.  
  
 `threadId`  
 in Die ID des Threads, bei dem es sich um den Bereich für das angeforderte statische Feld handelt.  
  
 `ppAddress`  
 vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich im angegebenen Thread befindet.  
  
## <a name="remarks"></a>Hinweise  

 Die- `GetThreadStaticAddress2` Methode kann eine der folgenden Methoden zurückgeben:  
  
- Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.  
  
- Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden. Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.  
  
 Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, `GetThreadStaticAddress2` gibt CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte mit rooting erstellt wurden.  
  
 Die [ICorProfilerInfo2:: GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) -Methode ähnelt der- `GetThreadStaticAddress2` Methode, akzeptiert jedoch kein Anwendungs Domänen Argument.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
