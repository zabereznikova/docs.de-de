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
ms.openlocfilehash: e4a003b30c495852a3a68d44d92bef35c3ed7812
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866295"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize-Methode
Wird aufgerufen, um den Codeprofiler zu initialisieren, wenn eine neue Common Language Runtime-Anwendung (CLR) gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parameters

- `pICorProfilerInfoUnk`

  \[in] Zeiger auf eine [IUnknown](/cpp/atl/iunknown) -Schnittstelle, die der Profiler nach einem [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstellen Zeiger Abfragen muss.  

## <a name="remarks"></a>Hinweise  
 Der `Initialize` Aufruf ist die einzige Möglichkeit, Rückrufe zu aktivieren (oder zu deaktivieren), die unveränderlich sind. Nachdem ein Rückruf durch den `Initialize`-Befehl aktiviert wurde, kann er später nicht mithilfe von " [ICorProfilerInfo::](icorprofilerinfo-seteventmask-method.md)abeinstellungs Maske" deaktiviert werden. Der COR_PRF_MONITOR_IMMUTABLE Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration gibt an, welche Ereignisse unveränderlich sind.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [Shutdown-Methode](icorprofilercallback-shutdown-method.md)
