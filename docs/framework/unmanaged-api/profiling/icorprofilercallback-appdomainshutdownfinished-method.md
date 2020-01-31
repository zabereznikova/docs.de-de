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
ms.openlocfilehash: 0851ac33a2bac4fcf727cf09e5225f6b83481b50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866675"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>ICorProfilerCallback::AppDomainShutdownFinished-Methode
Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parameters

- `appDomainId`

  \[in] identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert werden.

- `hrStatus`

  \[in] ein HRESULT, das angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.

## <a name="remarks"></a>Hinweise  
 Der Wert `appDomainId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) -Methode zurückgegeben wurde.  
  
 Einige Teile des Entladen der Anwendungsdomäne können nach dem `AppDomainCreationFinished` Rückruf fortgesetzt werden. Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin. Ein HRESULT mit Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
