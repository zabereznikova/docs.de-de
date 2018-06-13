---
title: ICorProfilerCallback::AppDomainShutdownFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f9f8925630933e2247726f92a93cac67bdc55ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450488"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>ICorProfilerCallback::AppDomainShutdownFinished-Methode
Benachrichtigt den Profiler, dass eine Anwendungsdomäne aus einem Prozess entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 `appDomainId`  
 [in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.  
  
 `hrStatus`  
 [in] Ein HRESULT, das angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der `appDomainId` gilt nicht für eine Anforderung Informationen nach der [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) -Methode zurückkehrt.  
  
 Einige Teile der Entladen der Anwendungsdomäne möglicherweise weiterhin nach dem `AppDomainCreationFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Entladen der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
