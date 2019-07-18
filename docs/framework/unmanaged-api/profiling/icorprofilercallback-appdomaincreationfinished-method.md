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
ms.openlocfilehash: 910f8b7f78b6348ace9036d35c0844f2a64cf433
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763140"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>ICorProfilerCallback::AppDomainCreationFinished-Methode
Benachrichtigt den Profiler an, dass eine Anwendungsdomäne erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a>Parameter  
 `appDomainId`  
 [in] Gibt die Domäne, die erstellt wurde.  
  
 `hrStatus`  
 [in] Ein HRESULT, der angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen.  
  
## <a name="remarks"></a>Hinweise  
 Die Anwendungs-ID ist ungültig für jede informationsanforderung, bis die `AppDomainCreationFinished` Methode wird aufgerufen.  
  
 Laden Sie die Anwendungsdomäne möglicherweise weiterhin nach den `AppDomainCreationFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil der Erstellung der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
