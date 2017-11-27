---
title: COR_PRF_GC_ROOT_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f340f9ad83d28b00054a0997bf4b60c750192bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootflags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS-Enumeration
Gibt eine Eigenschaft der Garbage Collection-Stamm.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|Der Stamm wird verhindert, dass eine Garbagecollection, dass das Objekt verschoben werden.|  
|`COR_PRF_GC_ROOT_WEAKREF`|Der Stamm verhindert keine Garbagecollection.|  
|`COR_PRF_GC_ROOT_INTERIOR`|Der Stamm bezieht sich auf ein Feld des Objekts statt das Objekt selbst.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|Der Stamm verhindert die Garbagecollection auf, wenn der Verweiszähler des Objekts einen bestimmten Wert ist.|  
  
## <a name="remarks"></a>Hinweise  
 `COR_PRF_GC_ROOT_FLAGS`ist eine Bitmaske, die Weitere Informationen zu besonderen Stämmen bereitstellt. Allerdings sind nicht alle Stämme besondere. Beispielsweise sind einige Stämme nicht schwache Verweise, inneren Zeigern, die angeheftet oder mit verweiszählung. Für solche Stämme sind keine Flags zu vermitteln. Aus diesem Grund Methoden, die diese Enumeration, z. B. verwenden die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode senden 0 für die Flags-Bitmaske, die angibt, dass alle flags deaktiviert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
