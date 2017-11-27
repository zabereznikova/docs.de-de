---
title: ICLRTaskManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3144338ddce262aaa6772f588a4f1a652cc57e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager-Schnittstelle
Enthält Methoden, die dem Host explizit anfordern, die die common Language Runtime (CLR) ermöglichen, Erstellen eines neuen Tasks, die aktuell ausgeführte Aufgabe erhalten und die geografische Sprache und Kultur für den Task festlegen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Fordert explizit an, dass die CLR erstellen Sie ein neues [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.|  
|[GetCurrentTask-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Ruft die `ICLRTask` -Instanz, die die Aufgabe darstellt, die gerade ausgeführt wird.|  
|[GetCurrentTaskType-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Ruft den Typ der Aufgabe, die gerade ausgeführt wird.|  
|[SetLocale-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Benachrichtigt die CLR, dass der Host den Gebietsschemabezeichner für die aktuell ausgeführte Aufgabe geändert hat.|  
|[SetUILocale-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Benachrichtigt der common Language Runtime, dass der Host den Gebietsschemabezeichner der Benutzeroberfläche für die aktuell ausgeführte Aufgabe geändert hat.|  
  
## <a name="remarks"></a>Hinweise  
 Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird verfügt über Darstellungen, die beide auf der Hostseite (eine Instanz von [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) und auf der CLR-Seite (eine Instanz von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). Der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die hostseitige Darstellung muss mit einer entsprechenden CLR-Seite-Darstellung, um sicherzustellen, dass erfolgreiche Kommunikation zwischen dem Host und der CLR in Bezug auf die Aufgabe verknüpft werden. Die beiden Objekte müssen erstellt und instanziiert wird, bevor verwalteter Code auf einem Betriebssystem-Thread ausgeführt werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
