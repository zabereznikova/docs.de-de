---
title: ICorProfilerCallback5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: ce34d43091cdee0bca88f94711e49072fa4fd08c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430063"
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5-Schnittstelle
Ergänzt Informationen, um einem Profiler zu helfen, den vollständigen Abschluss von Live-Objekten zu identifizieren, wenn er mit der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) -Methode oder der [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode zusammen mit den [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) -und [conditionalweaktableelementreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) -Methoden verwendet wird.  
  
 `ICorProfilerCallback5` müssen von einem verwalteten arbeitsspeicherprofiler implementiert werden, um Benachrichtigungen zu abonnieren, die mit abhängigen Handles verknüpft sind.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
