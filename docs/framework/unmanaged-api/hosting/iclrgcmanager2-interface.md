---
title: ICLRGCManager2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a8b51cf4297c1ccadbef8730c06148263d310e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2-interface"></a>ICLRGCManager2-Schnittstelle
Enthält Methoden, die einen Host für die Interaktion mit der common Language Runtime, Garbage Collection-System zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetGCStartupLimitsEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|Legt die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0. Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).  
  
 Die common Language Runtime (CLR) implementiert, die Garbage Collection-Mechanismus, mit der verwalteten <xref:System.GC> Typ. Weitere Informationen zur Garbage Collection-Systems finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Automatische Speicherverwaltung](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS-Struktur](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
