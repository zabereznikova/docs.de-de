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
ms.openlocfilehash: 174486a88192bd5ff11074930d5ad3375603f8a5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449457"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS-Enumeration
Gibt eine Eigenschaft eines Garbage Collection Stamms an.  
  
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
|`COR_PRF_GC_ROOT_PINNING`|Der Stamm verhindert, dass ein Garbage Collection das Objekt verschiebt.|  
|`COR_PRF_GC_ROOT_WEAKREF`|Der Stamm verhindert keine Garbage Collection.|  
|`COR_PRF_GC_ROOT_INTERIOR`|Der Stamm verweist auf ein Feld des-Objekts und nicht auf das-Objekt selbst.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|Der Stamm verhindert die Garbage Collection, wenn der Verweis Zähler des Objekts ein bestimmter Wert ist.|  
  
## <a name="remarks"></a>Hinweise  
 `COR_PRF_GC_ROOT_FLAGS` ist eine Bitmaske, die zusätzliche Informationen zu speziellen Stämmen bereitstellt. Allerdings sind nicht alle Stämme speziell. Einige Stämme sind z. b. keine schwachen Verweise, inneren Zeiger, fixiert oder Verweis Zählung. Für solche Stämme gibt es keine zu über Mittelung. Daher senden Methoden, die diese Enumeration verwenden, wie z. b. die [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) -Methode, 0 für die Flags-Bitmaske, die angibt, dass alle Flags ausgeschaltet sind.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Profilerstellungsenumerationen](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
