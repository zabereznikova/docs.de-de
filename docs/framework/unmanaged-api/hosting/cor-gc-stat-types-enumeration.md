---
title: COR_GC_STAT_TYPES-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STAT_TYPES
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STAT_TYPES
helpviewer_keywords: COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4cf66026ecf92d0158a1010e82c078478c280f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corgcstattypes-enumeration"></a>COR_GC_STAT_TYPES-Enumeration
Gibt an, die Statistiken für eine Garbagecollection aufgezeichnet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration gibt an, welche Statistiken in der [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) Struktur sind, festgelegt werden, indem [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) Methode.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Datensätze werden die Anzahl der Garbage Collections für jede Generierung ausgeführt.|  
|`COR_GC_MEMORYUSAGE`|Datensätze einer speicherauslastung und Garbage Collection Größe Speicherstatistik.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl, GCHost.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [COR_GC_STATS-Struktur](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
