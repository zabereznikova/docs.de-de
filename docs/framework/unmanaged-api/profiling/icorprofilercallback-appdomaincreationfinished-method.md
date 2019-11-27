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
ms.openlocfilehash: eaf0ae2a1b86234495c1804cff8b74331b3e8021
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445274"
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
 `appDomainId`  
 in Identifiziert die Domäne, die erstellt wurde.  
  
 `hrStatus`  
 in Ein HRESULT, das angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Anwendungs-ID ist für eine beliebige Informationsanforderung erst gültig, wenn die `AppDomainCreationFinished`-Methode aufgerufen wird.  
  
 Einige Teile des Ladens der Anwendungsdomäne können nach dem `AppDomainCreationFinished` Rückruf fortgesetzt werden. Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin. Ein HRESULT mit Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil der Erstellung der Anwendungsdomäne erfolgreich war.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
