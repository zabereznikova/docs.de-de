---
title: COR_PRF_GC_ROOT_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 263c22a07f363c2752afb50779515de043976e93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207707"
---
# <a name="corprfgcrootflags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS-Enumeration
Gibt eine Eigenschaft von einer Garbage Collection-Stamm.  
  
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
|`COR_PRF_GC_ROOT_PINNING`|Der Stamm wird verhindert, dass eine Garbagecollection von Verschieben des Objekts.|  
|`COR_PRF_GC_ROOT_WEAKREF`|Der Stamm verhindert die automatische speicherbereinigung nicht.|  
|`COR_PRF_GC_ROOT_INTERIOR`|Der Stamm bezieht sich auf ein Feld eines Objekts anstatt auf das Objekt selbst.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|Der Stamm verhindert die Garbagecollection auf, wenn der Verweiszähler des Objekts auf einen bestimmten Wert ist.|  
  
## <a name="remarks"></a>Hinweise  
 `COR_PRF_GC_ROOT_FLAGS` ist eine Bitmaske, die zusätzliche Informationen zu besonderen Stämmen bereitstellt. Nicht alle Stammzertifizierungsstellen sind jedoch spezielle. Beispielsweise sind einige Stämme nicht schwache Verweise, inneren Zeigern, angeheftete oder mit referenzzählung. Für solche Stämme sind keine Flags zu vermitteln. Aus diesem Grund Methoden, mit denen diese Enumeration, wie z. B. die [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode, senden Sie 0 für die Flags-Bitmaske, die angibt, dass alle flags deaktiviert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
