---
title: COR_GC_THREAD_STATS-Struktur
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 25a90965dc5466b7cf1a07140705424cf2ba4cd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699234"
---
# <a name="cor_gc_thread_stats-structure"></a>COR_GC_THREAD_STATS-Struktur

Enthält Thread bezogene Statistiken für Garbage Collection.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`PerThreadAllocation`|Die Anzahl von Bytes im Arbeitsspeicher, die auf dem Thread zugeordnet ist, der der aktuellen Instanz zugeordnet ist `COR_GC_THREAD_STATS` . Diese Zahl wird bei jedem Garbage Collection der Generation 0 (null) auf 0 (null) gelöscht.|  
|`Flags`|Die Anzahl der Bytes, die bei der letzten Garbage Collection auf eine höhere Generation herauf gestuft wurden.|  
  
## <a name="remarks"></a>Hinweise  

 [ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md) nimmt einen Output-Parameter vom Typ an `COR_GC_THREAD_STATS` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](hosting-structures.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
