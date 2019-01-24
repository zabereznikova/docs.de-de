---
title: ICorProfilerCallback::ModuleAttachedToAssembly-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff819ab67b258dbc7b5cec937863753852b1fcc1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629318"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly-Methode
Benachrichtigt den Profiler, dass ein Modul, dessen übergeordnete Assembly der angeschlossen ist.  
  
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
 [in] Die ID der übergeordneten Assembly, die das Modul zugeordnet ist.  
  
## <a name="remarks"></a>Hinweise  
 Ein Modul kann durch eine Importadresstabelle (IAT), geladen werden, durch einen Aufruf von `LoadLibrary`, oder über einen Metadatenverweis. Daher hat das common Language Runtime (CLR)-Ladeprogramm mehrere Codepfade zur Bestimmung der Assembly, in der ein Modul befindet. Daher ist es möglich, dass Sie nach [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) aufgerufen wird, wird das Modul ist nicht bekannt, welche Assembly ist, und die übergeordnete Assembly-ID ist nicht möglich. Die `ModuleAttachedToAssembly` Methode wird aufgerufen, wenn das Modul, um die übergeordnete Assembly und die übergeordnete Assembly angefügt wird-ID abgerufen werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
