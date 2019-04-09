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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bad1cc71b9a27896141837a6d342f2cfe068fc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089730"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a>ICorProfilerAssemblyReferenceProvider-Schnittstelle
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ermöglicht es dem Profiler, die common Language Runtime (CLR) über Assemblyverweise zu informieren, die der Profiler im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddAssemblyReference-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|Informiert die CLR über Assemblyverweise, die der Profiler plant, fügen Sie in der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR übergibt den Profiler eine `ICorProfilerAssemblyReferenceProvider` -Schnittstellenobjekt im der [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf. Dies kann der Profiler die CLR über Assemblyverweise zu informieren, die der Profiler plant, später im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md). -Rückruf hinzufügt. Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.  
  
 Diese Schnittstelle kann nur in verwendet werden, die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf, der dieses Schnittstellenobjekt an den Profiler weitergibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
