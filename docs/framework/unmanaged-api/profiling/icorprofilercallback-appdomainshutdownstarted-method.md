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
ms.openlocfilehash: 6bbb41f8fd3ac37f1c21fe8b4f6159e3d303777c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445181"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a>ICorProfilerCallback::AppDomainShutdownStarted-Methode
Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a>Parameter  
 `appDomainId`  
 in Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert werden.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert von `appDomainId` ist für keine Informationsanforderung gültig, nachdem die `AppDomainShutdownStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Anwendungsdomäne zu erhalten.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
