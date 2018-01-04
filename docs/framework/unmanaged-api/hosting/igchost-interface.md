---
title: IGCHost-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77a2cab35785aa39571d39bdd369fa26cdbcd1d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="igchost-interface"></a>IGCHost-Schnittstelle
Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.  
  
> [!NOTE]
>  Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], können Sie die [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) -Methode die Größe der Garbage Collection-Segment und die maximale Größe der Generation 0, die Garbage Collection-System auf Werte größer als der `DWORD` Grenzwert, der vom auferlegt wird die [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) Methode.  
  
> [!NOTE]
>  Diese Schnittstelle ist für die Verwendung durch Experten nur. Er kann die Leistung einer Anwendung beeinträchtigen, wenn Sie nicht ordnungsgemäß verwendet.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Collect-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Erzwingt, dass eine Sammlung aus, für die angegebene Generation, unabhängig vom Zustand der aktuellen Garbagecollection durchgeführt.|  
|[GetStats-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems an.|  
|[GetThreadStats-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Ruft die Statistiken pro Thread für die Garbagecollection ab.|  
|[SetGCStartupLimits-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Legt die Größe des Segments und die maximale Größe für Generation 0 fest.|  
|[SetVirtualMemLimit-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl, GCHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
