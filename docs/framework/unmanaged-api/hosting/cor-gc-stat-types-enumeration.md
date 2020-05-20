---
title: COR_GC_STAT_TYPES-Enumeration
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: cca393ae34144787ab7800baec7c58209394f30e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616715"
---
# <a name="cor_gc_stat_types-enumeration"></a>COR_GC_STAT_TYPES-Enumeration
Gibt die Statistiken an, die für eine Garbage Collection aufgezeichnet werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) Struktur von der [ICLRGCManager:: GetStats](iclrgcmanager-getstats-method.md) -Methode festgelegt werden sollen.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Zeichnet die Anzahl der Garbage Collections auf, die für jede Generation ausgeführt werden.|  
|`COR_GC_MEMORYUSAGE`|Zeichnet Statistiken zur Speicherauslastung und Garbage Collection Größe auf.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [COR_GC_STATS-Struktur](cor-gc-stats-structure.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
