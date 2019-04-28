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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60a4b56270318a05d0e5a480fdb56eb45593d5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696717"
---
# <a name="corgcthreadstats-structure"></a>COR_GC_THREAD_STATS-Struktur
Enthält pro-Thread-Statistiken, die Garbagecollection betreffen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`PerThreadAllocation`|Die Anzahl der Bytes im Arbeitsspeicher reserviert, auf dem Thread, der mit dem aktuellen verknüpft ist `COR_GC_THREAD_STATS` Instanz. Diese Zahl ist 0 (null) bei jedem gelöscht eine Generation 0 Garbagecollection tritt auf.|  
|`Flags`|Die Anzahl der Bytes, die auf eine höhere Generation für die automatische speicherbereinigung auf das neueste höher gestuft.|  
  
## <a name="remarks"></a>Hinweise  
 [ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) nimmt einen Output-Parameter des Typs `COR_GC_THREAD_STATS`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
