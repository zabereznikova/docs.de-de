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
ms.openlocfilehash: 7e43f58f619aaa63fa2294dd3e989026dcdfc604
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866129"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a>ICorProfilerCallback::ModuleUnloadStarted-Methode
Benachrichtigt den Profiler, dass ein Modul entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a>Parameters  
 `moduleId`  
 in Die ID des Moduls, das entladen wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert `moduleId` ist für eine Informationsanforderung nicht gültig, nachdem die `ModuleUnloadStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu diesem Modul zu erhalten.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [ModuleUnloadFinished-Methode](icorprofilercallback-moduleunloadfinished-method.md)
