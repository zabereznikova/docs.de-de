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
ms.openlocfilehash: bcf5c5c9044a30fc8259dbc54bad8f3141f0f926
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733112"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly-Methode

Benachrichtigt den Profiler, dass ein Modul an die übergeordnete Assembly angefügt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Parameter  

 `moduleId`  
 in Die ID des Moduls, das angefügt wird.  
  
 `AssemblyId`  
 in Die ID der übergeordneten Assembly, an die das Modul angefügt wird.  
  
## <a name="remarks"></a>Hinweise  

 Ein Modul kann über eine Import Adress Tabelle (IAT), über einen-Rückruf `LoadLibrary` oder über einen Metadatenverweis geladen werden. Daher verfügt das Common Language Runtime (CLR)-Lade Modul über mehrere Codepfade zum Ermitteln der Assembly, in der sich ein Modul befindet. Daher ist es möglich, dass das Modul nach dem Aufruf von [ICorProfilerCallback:: moduleloadend](icorprofilercallback-moduleloadfinished-method.md) nicht weiß, in welcher Assembly es sich befindet und die übergeordnete Assembly-ID nicht abgerufen werden kann. Die `ModuleAttachedToAssembly` -Methode wird aufgerufen, wenn das Modul an die übergeordnete Assembly angefügt wird und die übergeordnete Assembly-ID abgerufen werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
