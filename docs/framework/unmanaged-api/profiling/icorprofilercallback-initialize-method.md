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
ms.openlocfilehash: cd53d74dfe8199617df47e46641b71203abf6e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452347"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize-Methode
Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue common Language Runtime (CLR)-Anwendung gestartet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pICorProfilerInfoUnk`  
 [in](/cpp/atl/iunknown) -Schnittstelle, die der Profiler für die Abfrage ausführen muss ein [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstellenzeiger auf.  
  
## <a name="remarks"></a>Hinweise  
 Die `Initialize` Aufruf ist die einzige Möglichkeit, unveränderliche Rückrufe aktivieren (oder deaktivieren). Sobald ein Rückruf, indem aktiviert ist die `Initialize` aufrufen, es kann nicht mit einem späteren Zeitpunkt deaktiviert werden [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Der COR_PRF_MONITOR_IMMUTABLE-Wert, der die [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration gibt an, welche Ereignisse unveränderlich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Shutdown-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
