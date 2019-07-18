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
ms.openlocfilehash: 7f179e3b01d6c3b34dfa765565a0fc38d0ba867c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753696"
---
# <a name="corprfgcrootflags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS-Enumeration
Gibt eine Eigenschaft von einer Garbage Collection-Stamm.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
