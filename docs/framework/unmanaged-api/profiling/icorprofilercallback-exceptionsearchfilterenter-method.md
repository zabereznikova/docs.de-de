---
title: ICorProfilerCallback::ExceptionSearchFilterEnter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFilterEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8196b9393a96619c17fa2771e3481cd47aafd4b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a>ICorProfilerCallback::ExceptionSearchFilterEnter-Methode
Benachrichtigt den Profiler, dass die Suchphase der Behandlung von Ausnahmen mit dem Ausführen eines benutzerdefinierten Ausnahmefilters begonnen hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die den Filter enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ExceptionSearchFilterLeave-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
