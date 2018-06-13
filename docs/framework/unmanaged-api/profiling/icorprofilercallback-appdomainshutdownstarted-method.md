---
title: ICorProfilerCallback::AppDomainShutdownStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd1e5daada8793e94980afc5f0cf509915bd288e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450927"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a>ICorProfilerCallback::AppDomainShutdownStarted-Methode
Benachrichtigt den Profiler, dass von einem Prozess eine Anwendungsdomäne entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `appDomainId`  
 [in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der `appDomainId` gilt nicht für jede Anforderung Informationen nach der `AppDomainShutdownStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen zu dieser Anwendungsdomäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
