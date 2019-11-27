---
title: ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 12c9b30dc72d1ccf7bfa79ca0745ba3f2c2290c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435875"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
Ruft die Adresse des angegebenen Anwendungs Domänen statischen Felds ab, das sich im Gültigkeitsbereich der angegebenen Anwendungsdomäne befindet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parameter  
 `classId`  
 in Die Klassen-ID der Klasse, die das angeforderte Feld für die Anwendungsdomäne enthält.  
  
 `fieldToken`  
 in Das Metadatentoken für das angeforderte Anwendungs Domänen-static-Feld.  
  
 `appDomainId`  
 in Die ID der Anwendungsdomäne, bei der es sich um den Bereich für das angeforderte statische Feld handelt.  
  
 `ppAddress`  
 vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich innerhalb der angegebenen Anwendungsdomäne befindet.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetAppDomainStaticAddress`-Methode kann eine der folgenden Methoden zurückgeben:  
  
- Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.  
  
- Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden. Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.  
  
 Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, gibt `GetAppDomainStaticAddress` CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte rooting.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
