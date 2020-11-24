---
title: ICorProfilerCallback::ModuleLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 5a29507ca56cac4ab800845e3a88706dc7a25379
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683991"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>ICorProfilerCallback::ModuleLoadFinished-Methode

Benachrichtigt den Profiler, dass ein Modul den Ladevorgang abgeschlossen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parameter  

 `moduleId`  
 in Die ID des Moduls, das den Ladevorgang abgeschlossen hat.  
  
 `hrStatus`  
 in Ein HRESULT, das angibt, ob das Modul erfolgreich geladen wurde.  
  
## <a name="remarks"></a>Hinweise  

 Der Wert von `moduleId` ist für eine Informationsanforderung erst gültig, wenn die- `ModuleLoadFinished` Methode aufgerufen wird.  
  
 Einige Teile des Ladens des Moduls können nach dem Rückruf fortgesetzt werden `ModuleLoadFinished` . Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin. Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens des Moduls erfolgreich war.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ModuleLoadStarted-Methode](icorprofilercallback-moduleloadstarted-method.md)
