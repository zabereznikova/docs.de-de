---
title: ICorProfilerCallback::ModuleUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a4637ac7466a575c94f8244168576c4a5542689
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452087"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>ICorProfilerCallback::ModuleUnloadFinished-Methode
Benachrichtigt den Profiler, dass ein Modul entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, der entladen wurde.  
  
 `hrStatus`  
 [in] Ein HRESULT, das angibt, ob das Modul erfolgreich entladen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der `moduleId` gilt nicht für eine Anforderung Informationen nach der [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) -Methode zurückkehrt.  
  
 Einige Teile der Entladen der Klasse möglicherweise weiterhin nach dem `ModuleUnloadFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil des Moduls entladen erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
