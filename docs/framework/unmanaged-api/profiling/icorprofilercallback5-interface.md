---
title: ICorProfilerCallback5-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0406b537f6f20d7194a0115020245ade101bd498
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5-Schnittstelle
Ergänzt Informationen, um einen Profiler den vollständigen Abschluss von aktiven Objekten zu identifizieren, bei Verwendung entweder mit Hilfe der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) oder [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)-Methode zusammen mit der [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) und [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) Methoden.  
  
 `ICorProfilerCallback5`muss von einem Profiler verwalteten Speicher zum Abonnieren von Benachrichtigungen im Zusammenhang mit abhängigen Handles implementiert werden.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
