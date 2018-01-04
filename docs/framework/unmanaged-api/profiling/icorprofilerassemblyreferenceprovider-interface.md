---
title: ICorProfilerAssemblyReferenceProvider-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerAssemblyReferenceProvider
api_location: mscorwks.dll
api_type: COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 203362d2780d372236b05f753bedc0d59565d2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a>ICorProfilerAssemblyReferenceProvider-Schnittstelle
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ermöglicht es dem Profiler an die common Language Runtime (CLR) über Assemblyverweise zu informieren, die der Profiler im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddAssemblyReference-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|Informiert die CLR einen Assemblyverweis, die der Profiler plant, fügen Sie in der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR übergibt den Profiler eine `ICorProfilerAssemblyReferenceProvider` Schnittstellenobjekt, das in der [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf. Dies ermöglicht es dem Profiler, die CLR über Assemblyverweise zu informieren, die der Profiler plant, die später im Hinzufügen der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md). -Rückruf hinzufügt. Dies verbessert die Genauigkeit des Assemblyverweis-Abschlussdurchlaufs der CLR sowie dessen Algorithmen zur Bestimmung, ob Assemblys geteilt werden können.  
  
 Diese Schnittstelle kann nur in verwendet das [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückruf, der dieses Schnittstellenobjekt an den Profiler weitergibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
