---
title: ICorProfilerCallback::ModuleUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: c7ad94bf766e0fcdbff95b0766cf68c2196a2c71
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503331"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a>ICorProfilerCallback::ModuleUnloadStarted-Methode
Benachrichtigt den Profiler, dass ein Modul entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 in Die ID des Moduls, das entladen wird.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Wert von `moduleId` ist für eine Informationsanforderung nach dem `ModuleUnloadStarted` zurückkehren der Methode ungültig – Dies ist die letzte Möglichkeit des Profilers, Informationen zu diesem Modul zu erhalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ModuleUnloadFinished-Methode](icorprofilercallback-moduleunloadfinished-method.md)
