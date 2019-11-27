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
ms.openlocfilehash: 08fbf49e6944de4934a9fe7a960405ee96a7d8e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445938"
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
 Der Wert `moduleId` ist für eine Informationsanforderung erst gültig, wenn die `ModuleLoadFinished`-Methode aufgerufen wird.  
  
 Einige Teile des Ladens des Moduls können nach dem `ModuleLoadFinished` Rückruf fortgesetzt werden. Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin. Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens des Moduls erfolgreich war.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ModuleLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)
