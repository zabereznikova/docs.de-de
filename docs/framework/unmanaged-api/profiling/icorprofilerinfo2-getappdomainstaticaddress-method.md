---
title: ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetAppDomainStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type: apiref
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
Ruft die Adresse des Felds Domäne statische angegebenen Anwendung, die im Rahmen der angegebenen Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die Klassen-ID der Klasse, die die angeforderte Domäne statische Feld enthält.  
  
 `fieldToken`  
 [in] Das Metadatentoken für die angeforderte Domäne statische Feld.  
  
 `appDomainId`  
 [in] Die ID der Anwendungsdomäne, die den Bereich für die angeforderten statischen Felds ist.  
  
 `ppAddress`  
 [out] Ein Zeiger auf die Adresse des statischen Felds, das in die angegebene Anwendungsdomäne ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetAppDomainStaticAddress` Methode kann einen der folgenden zurück:  
  
-   Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.  
  
-   Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap. Diese Adressen möglicherweise nach der Garbagecollection, ungültig werden, damit nach der Garbagecollection Profiler nicht annehmen soll, dass sie gültig sind.  
  
 Vor dem Abschluss einer Klasse Klassenkonstruktor `GetAppDomainStaticAddress` wird CORPROF_E_DATAINCOMPLETE für alle seine statischen Felder zurück, obwohl einige statische Felder möglicherweise bereits initialisiert und rooting Garbage Collection-Objekten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
