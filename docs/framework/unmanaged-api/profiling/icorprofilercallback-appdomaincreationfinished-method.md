---
title: ICorProfilerCallback::AppDomainCreationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0017cff43f7a1b1bdd90806f50abb374a96dadf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450423"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished-Methode
Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a>Parameter  
 `appDomainId`  
 [in] Identifiziert die Domäne, die erstellt wurde.  
  
 `hrStatus`  
 [in] Ein HRESULT, das angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen.  
  
## <a name="remarks"></a>Hinweise  
 Die Anwendungs-ID ist ungültig für jede Anforderung Informationen, bis die `AppDomainCreationFinished` -Methode aufgerufen wird.  
  
 Einige Teile die Anwendungsdomäne laden möglicherweise weiterhin nach dem `AppDomainCreationFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Erstellens der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
