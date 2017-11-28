---
title: ICorProfilerInfo2::GetRVAStaticAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetRVAStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64553e8f611a8111aaaf9ababd1a7556f1192740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>ICorProfilerInfo2::GetRVAStaticAddress-Methode
Ruft die Adresse des angegebenen relativen virtuellen Adresse (RVA) statischen Felds ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die ID der Klasse, die das angeforderte RVA-statische Feld enthält.  
  
 `fieldToken`  
 [in] Das Metadatentoken für die angeforderte RVA-statische Feld.  
  
 `ppAddress`  
 [out] Ein Zeiger auf die Adresse des RVA statischen Felds.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetRVAStaticAddress` Methode kann einen der folgenden zurück:  
  
-   Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.  
  
-   Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap. Diese Adressen möglicherweise nach der Garbagecollection, ungültig werden, damit nach der Garbagecollection Profiler nicht annehmen soll, dass sie gültig sind.  
  
 Vor dem Abschluss einer Klasse Klassenkonstruktor `GetRVAStaticAddress` für alle seine statische Felder, obwohl einige statische Felder sind möglicherweise bereits initialisiert und Garbage Collection-Objekten Stamm CORPROF_E_DATAINCOMPLETE zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
