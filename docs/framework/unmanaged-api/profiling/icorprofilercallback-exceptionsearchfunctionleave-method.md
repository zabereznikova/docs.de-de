---
title: ICorProfilerCallback::ExceptionSearchFunctionLeave-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e63309ea1d92018b41c8ee32fcd66f865af5d891
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a>ICorProfilerCallback::ExceptionSearchFunctionLeave-Methode
Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung Suche in einer Funktion abgeschlossen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ExceptionSearchFunctionEnter-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
