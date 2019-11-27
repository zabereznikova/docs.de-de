---
title: ICorProfilerCallback::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 64df6a81eb23c20537238c702fd0c204d64d14bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434549"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize-Methode
Wird aufgerufen, um den Codeprofiler zu initialisieren, wenn eine neue Common Language Runtime-Anwendung (CLR) gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parameter  
 `pICorProfilerInfoUnk`  
 [in](/cpp/atl/iunknown) der Schnittstelle, die der Profiler nach einem [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) -Schnittstellen Zeiger Abfragen muss.  
  
## <a name="remarks"></a>Hinweise  
 Der `Initialize` Aufruf ist die einzige Möglichkeit, Rückrufe zu aktivieren (oder zu deaktivieren), die unveränderlich sind. Nachdem ein Rückruf durch den `Initialize`-Befehl aktiviert wurde, kann er später nicht mithilfe von " [ICorProfilerInfo::](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)abeinstellungs Maske" deaktiviert werden. Der COR_PRF_MONITOR_IMMUTABLE Wert der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration gibt an, welche Ereignisse unveränderlich sind.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
