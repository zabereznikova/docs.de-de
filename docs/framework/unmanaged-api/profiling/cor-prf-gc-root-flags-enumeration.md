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
ms.openlocfilehash: bbc163c71b47e6fee0db89284d6e3fd27e882768
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500885"
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
  
## <a name="remarks"></a>Bemerkungen  
 `COR_PRF_GC_ROOT_FLAGS`ist eine Bitmaske, die zusätzliche Informationen über spezielle Stämme bereitstellt. Allerdings sind nicht alle Stämme speziell. Einige Stämme sind z. b. keine schwachen Verweise, inneren Zeiger, fixiert oder Verweis Zählung. Für solche Stämme gibt es keine zu über Mittelung. Daher senden Methoden, die diese Enumeration verwenden, wie z. b. die [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) -Methode, 0 für die Flags-Bitmaske, die angibt, dass alle Flags ausgeschaltet sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Profilerstellungsenumerationen](profiling-enumerations.md)
