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
ms.openlocfilehash: ddb2d6eeb75a118a12f681b354f6feccd1231c64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685380"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>ICorProfilerCallback::AppDomainShutdownFinished-Methode

Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parameter

- `appDomainId`

  \[in] identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert werden.

- `hrStatus`

  \[in] ein HRESULT, das angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.

## <a name="remarks"></a>Hinweise  

 Der Wert von `appDomainId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) -Methode zurückgegeben wurde.  
  
 Einige Teile des Entladen der Anwendungsdomäne können nach dem Rückruf fortgesetzt werden `AppDomainCreationFinished` . Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin. Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
