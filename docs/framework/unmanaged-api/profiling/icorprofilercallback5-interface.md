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
ms.openlocfilehash: 8e94aebc489fff1c81593e54b17c471e7228d810
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689289"
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5-Schnittstelle

Ergänzt Informationen, um einem Profiler zu helfen, den vollständigen Abschluss von Live-Objekten zu identifizieren, wenn er mit der [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) -Methode oder der [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) -Methode zusammen mit den [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) -und [conditionalweaktableelementreferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) -Methoden verwendet wird.  
  
 `ICorProfilerCallback5` muss von einem verwalteten arbeitsspeicherprofiler implementiert werden, um Benachrichtigungen zu abonnieren, die mit abhängigen Handles verknüpft sind.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences-Methode](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Identifiziert den transitiven Abschluss von Objekten, auf die durch diese Stammelemente verwiesen wird, sowohl über direkte Memberfeldverweise, als auch `ConditionalWeakTable`-Abhängigkeiten.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [ICorProfilerCallback2-Schnittstelle](icorprofilercallback2-interface.md)
