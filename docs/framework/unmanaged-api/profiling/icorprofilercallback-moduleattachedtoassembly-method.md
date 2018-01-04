---
title: ICorProfilerCallback::ModuleAttachedToAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleAttachedToAssembly
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6183014bf5487d0eebccf2fb70a13c363212046b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly-Methode
Benachrichtigt den Profiler, dass ein Modul an seine übergeordnete Assembly verbunden ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, die angefügt wird.  
  
 `AssemblyId`  
 [in] Die ID der übergeordneten Assembly, die das Modul angeschlossen ist.  
  
## <a name="remarks"></a>Hinweise  
 Ein Modul kann durch eine Importadresstabelle (IAT), geladen werden, durch einen Aufruf von `LoadLibrary`, oder durch einen Metadatenverweis. Folglich weist das common Language Runtime (CLR)-Ladeprogramm mehrere Codepfade zur Bestimmung der Assembly, in der ein Modul aktiv ist. Daher ist es möglich, dass nach dem [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) aufgerufen wird, wird das Modul weiß nicht, welche Assembly befindet sich im und Abrufen der übergeordneten Assembly-ID ist nicht möglich. Die `ModuleAttachedToAssembly` Methode wird aufgerufen, wenn das Modul, um die übergeordnete Assembly und der übergeordneten Assembly angeschlossen ist-ID abgerufen werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
