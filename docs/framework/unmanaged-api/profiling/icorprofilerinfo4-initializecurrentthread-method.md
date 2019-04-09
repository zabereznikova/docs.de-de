---
title: ICorProfilerInfo4::InitializeCurrentThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fd0900e61c57d105439d83430284dc8634d2a1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223601"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread-Methode
Initialisiert den aktuellen Thread im Voraus über nachfolgende Profiler, die auf dem gleichen Thread, API-Aufrufe, sodass dieser Deadlock vermieden werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Es wird empfohlen, die Sie aufrufen `InitializeCurrentThread` auf einem beliebigen Thread, der einen Profiler aufruft, API, die es zwar Threads angehalten. Diese Methode wird in der Regel von beispielprofilern, das Erstellen von eigenen Thread aufrufen, verwendet der [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode zum Durchführen der Stapel führt während der Zielthread angehalten ist. Durch Aufrufen von `InitializeCurrentThread` , nachdem der Profiler Wenn zunächst den Sampling-Thread erstellt, Profiler können sicherstellen, dass die pro Thread verzögerte Initialisierung, die die CLR beim ersten Aufruf andernfalls ausführen würden `DoStackSnapshot` kann nun erfolgen sicher Wenn keine anderen Threads sind angehalten.  
  
> [!NOTE]
>  `InitializeCurrentThread` führt die Initialisierung im voraus, um Aufgaben abgeschlossen sind, die Sperren, und kann zu einem deadlock. Rufen Sie `InitializeCurrentThread` nur, wenn keine angehaltenen Threads vorhanden sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
