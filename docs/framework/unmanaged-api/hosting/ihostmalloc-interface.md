---
title: IHostMalloc-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc
helpviewer_keywords: IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a>IHostMalloc-Schnittstelle
Enthält Methoden, die die common Language Runtime (CLR) zum Anfordern von differenzierter Zuordnungen aus dem Heap über den Host zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Alloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap belegen.|  
|[DebugAlloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap reserviert und außerdem nachverfolgt, in dem der Speicher belegt wurde.|  
|[Free-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Speicher, der mit belegt wurde freigegeben wird die `Alloc` Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft einen Schnittstellenzeiger auf eine `IHostMalloc` Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
