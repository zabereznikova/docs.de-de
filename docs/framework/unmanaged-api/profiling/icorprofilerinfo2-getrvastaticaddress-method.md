---
title: ICorProfilerInfo2::GetRVAStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc7b6d1a27faf7bde46305f9c98d98351e6261b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782270"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>ICorProfilerInfo2::GetRVAStaticAddress-Methode
Ruft die Adresse des statischen Felds angegebene relative virtuelle Adresse (RVA).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die ID der Klasse, die das angeforderte RVA-statische Feld enthält.  
  
 `fieldToken`  
 [in] Das Metadatentoken für das angeforderte RVA-statische Feld.  
  
 `ppAddress`  
 [out] Ein Zeiger auf die Adresse des RVA statischen Felds.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRVAStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:  
  
- Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.  
  
- Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap. Diese Adressen können nach der Garbagecollection, ungültig werden. daher nach der Garbagecollection, Profiler nicht davon auszugehen, dass sie gültig sind.  
  
 Vor dem Abschluss einer Klasse Klassenkonstruktor `GetRVAStaticAddress` für alle seine statische Felder, obwohl einige statische Felder sind möglicherweise bereits initialisiert und Garbage Collection-Objekten Stamm CORPROF_E_DATAINCOMPLETE zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
