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
ms.openlocfilehash: ea4fc8ab39d616415106150f56f4b7afd5f68237
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500103"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize-Methode
Wird aufgerufen, um den Codeprofiler zu initialisieren, wenn eine neue Common Language Runtime-Anwendung (CLR) gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parameter

- `pICorProfilerInfoUnk`

  \[in] Zeiger auf eine [IUnknown](/cpp/atl/iunknown) -Schnittstelle, die der Profiler nach einem [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstellen Zeiger Abfragen muss.  

## <a name="remarks"></a>Bemerkungen  
 Der `Initialize` Aufruf ist die einzige Möglichkeit, Rückrufe zu aktivieren (oder zu deaktivieren), die unveränderlich sind. Nachdem ein Rückruf durch den-Befehl aktiviert `Initialize` wurde, kann er später nicht mithilfe von [ICorProfilerInfo::](icorprofilerinfo-seteventmask-method.md)absetzendebuggerinfo deaktiviert werden. Der COR_PRF_MONITOR_IMMUTABLE Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration gibt an, welche Ereignisse unveränderlich sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [Shutdown-Methode](icorprofilercallback-shutdown-method.md)
