---
title: ICLRMemoryNotificationCallback-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMemoryNotificationCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMemoryNotificationCallback
helpviewer_keywords: ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b998f8af2c7f4add3ecbb905928b5956409bf00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback-Schnittstelle
Der Host kann mit einem Ansatz ähnelt der des Win32-speicherauslastung des Berichts `CreateMemoryResourceNotification` Funktion.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[OnMemoryNotification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.|  
  
## <a name="remarks"></a>Hinweise  
 Vom Host verwendet die `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Geben Sie Arbeitsspeicherressourcen frei.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
