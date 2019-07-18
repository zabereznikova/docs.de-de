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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e50421dc15dd30f1811dbe5ebef2ff2f7a0a9483
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755821"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize-Methode
Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue common Language Runtime (CLR)-Anwendung gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parameter  
 `pICorProfilerInfoUnk`  
 [in](/cpp/atl/iunknown) -Schnittstelle, die der Profiler für die Abfrage muss eine [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstellenzeiger auf.  
  
## <a name="remarks"></a>Hinweise  
 Die `Initialize` Aufruf ist die einzige Möglichkeit zu aktivieren (oder deaktivieren) Sie Rückrufe, die unveränderlich sind. Nachdem Sie ein Rückruf aktiviert ist, indem die `Initialize` aufrufen, er kann nicht mit einem späteren Zeitpunkt deaktiviert werden [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Die COR_PRF_MONITOR_IMMUTABLE-Wert, der die [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration gibt an, welche Ereignisse unveränderlich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
