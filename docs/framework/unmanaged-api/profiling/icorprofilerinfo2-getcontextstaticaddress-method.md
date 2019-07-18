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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c5c8165d44cc3a305820f8e97c07da37f2a0693
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775809"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>ICorProfilerInfo2::GetContextStaticAddress-Methode
Ruft die Adresse für das angegebene kontextstatische-Feld, das im Rahmen des angegebenen Kontexts.  
  
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
 [in] Die ID der Klasse, die das angeforderte kontextstatische-Feld enthält.  
  
 `fieldToken`  
 [in] Das Metadatentoken für das angeforderte kontextstatische-Feld.  
  
 `contextId`  
 [in] Die ID des Kontexts, der den Bereich für die angeforderte statische Feld des Kontexts ist.  
  
 `ppAddress`  
 [out] Ein Zeiger auf die Adresse eines statischen Felds, das innerhalb des angegebenen Kontexts.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetContextStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:  
  
- Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.  
  
- Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap. Diese Adressen können nach der Garbagecollection, ungültig werden. daher nach der Garbagecollection, Profiler nicht davon auszugehen, dass sie gültig sind.  
  
 Vor dem Abschluss einer Klasse Klassenkonstruktor `GetContextStaticAddress` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
