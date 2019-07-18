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
ms.openlocfilehash: 8dd5e2ecf22ce14765df8972611f1f95109f76ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769197"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>ICorProfilerCallback::ModuleUnloadFinished-Methode
Benachrichtigt den Profiler, dass ein Modul entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, das entladen wurde.  
  
 `hrStatus`  
 [in] Ein HRESULT, der angibt, ob das Modul erfolgreich entladen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des `moduleId` gilt nicht für eine informationsanforderung nach der [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) Methodenrückgabe.  
  
 Das Entladen der Klasse möglicherweise weiterhin nach den `ModuleUnloadFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil des Entladevorgangs für das Modul erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
