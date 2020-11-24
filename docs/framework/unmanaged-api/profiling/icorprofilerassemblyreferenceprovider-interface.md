---
title: ICorProfilerAssemblyReferenceProvider-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 2cee012be2665f5a7212600ec11e401b18160d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691395"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a>ICorProfilerAssemblyReferenceProvider-Schnittstelle

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ermöglicht es dem Profiler, die Common Language Runtime (CLR) der Assemblyverweise zu informieren, die der Profiler im [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzufügt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AddAssemblyReference-Methode](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|Informiert die CLR über einen Assemblyverweis, den der Profiler plant, im [moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzuzufügen.|  
  
## <a name="remarks"></a>Hinweise  

 Die CLR übergibt dem Profiler ein `ICorProfilerAssemblyReferenceProvider` Schnittstellen Objekt im [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf. Dies ermöglicht es dem Profiler, die CLR der Assemblyverweise zu informieren, die der Profiler später in [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md)hinzufügen möchte. -Rückruf hinzufügt. Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.  
  
 Diese Schnittstelle kann nur im [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf verwendet werden, der dieses Schnittstellen Objekt an den Profiler übergibt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Profilerstellungsschnittstellen](profiling-interfaces.md)
