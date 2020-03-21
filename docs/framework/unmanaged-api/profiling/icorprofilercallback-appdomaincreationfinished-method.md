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
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177071"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished-Methode
Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a>Parameter

- `appDomainId`

  \[in] Identifiziert die erstellte Domäne.

- `hrStatus`

  \[in] Ein HRESULT, das angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen wurde.

## <a name="remarks"></a>Bemerkungen  
 Die Anwendungs-ID ist für Informationsanforderung `AppDomainCreationFinished` nicht gültig, bis die Methode aufgerufen wird.  
  
 Einige Teile des Ladens der `AppDomainCreationFinished` Anwendungsdomäne werden möglicherweise nach dem Rückruf fortgesetzt. Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin. Ein erfolgreicher HRESULT `hrStatus` in zeigt jedoch nur an, dass der erste Teil des Erstellens der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
