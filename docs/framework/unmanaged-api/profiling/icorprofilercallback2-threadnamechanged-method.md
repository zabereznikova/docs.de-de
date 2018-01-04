---
title: ICorProfilerCallback2::ThreadNameChanged-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.ThreadNameChanged
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ef0100111aa64aed2df7c63c332b54f026d1e26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2threadnamechanged-method"></a>ICorProfilerCallback2::ThreadNameChanged-Methode
Benachrichtigt den Profiler, dass der Name eines Threads geändert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `threadId`  
 [in] Die ID des Threads.  
  
 `cchName`  
 [in] Die Länge des neuen Namens des Threads.  
  
 `name`  
 [in] Der neue Name des Threads. Der Name ist nicht mit Null beendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
