---
title: ICorProfilerCallback::AssemblyLoadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48453532177b1e619f4f863e7297345566637d4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a>ICorProfilerCallback::AssemblyLoadStarted-Methode
Benachrichtigt den Profiler, dass eine Assembly geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `assemblyId`  
 [in] Identifiziert die Assembly, die geladen wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der `assemblyId` gilt nicht für eine Anforderung Informationen, bis die [ICorProfilerCallback:: AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) Methode wird aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
