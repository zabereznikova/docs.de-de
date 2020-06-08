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
ms.openlocfilehash: 4f494919d11e0f979cf1964c08106fbb9b9ed20b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503392"
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
  
## <a name="remarks"></a>Bemerkungen  
 Ein Modul kann über eine Import Adress Tabelle (IAT), über einen-Rückruf `LoadLibrary` oder über einen Metadatenverweis geladen werden. Daher verfügt das Common Language Runtime (CLR)-Lade Modul über mehrere Codepfade zum Ermitteln der Assembly, in der sich ein Modul befindet. Daher ist es möglich, dass das Modul nach dem Aufruf von [ICorProfilerCallback:: moduleloadend](icorprofilercallback-moduleloadfinished-method.md) nicht weiß, in welcher Assembly es sich befindet und die übergeordnete Assembly-ID nicht abgerufen werden kann. Die `ModuleAttachedToAssembly` -Methode wird aufgerufen, wenn das Modul an die übergeordnete Assembly angefügt wird und die übergeordnete Assembly-ID abgerufen werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
