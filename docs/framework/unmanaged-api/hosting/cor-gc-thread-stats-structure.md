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
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178268"
---
# <a name="cor_gc_thread_stats-structure"></a>COR_GC_THREAD_STATS-Struktur
Enthält Pro-Thread-Statistiken zur Garbage Collection.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`PerThreadAllocation`|Die Anzahl der Bytes an Arbeitsspeicher, die `COR_GC_THREAD_STATS` dem Thread zugewiesen sind, der der aktuellen Instanz zugeordnet ist. Diese Zahl wird jedes Mal auf Null gelöscht, wenn eine Garbage Collection von Generation Null stattfindet.|  
|`Flags`|Die Anzahl der Bytes, die bei der letzten Garbage Collection auf eine höhere Generation heraufgestuft wurden.|  
  
## <a name="remarks"></a>Bemerkungen  
 [ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) nimmt einen Ausgabeparameter vom Typ `COR_GC_THREAD_STATS`an.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** GCHost.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
