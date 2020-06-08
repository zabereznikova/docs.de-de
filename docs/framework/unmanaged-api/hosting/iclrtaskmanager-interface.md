---
title: ICLRTaskManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: f918d4e7b95922734d70ed832581e6c494c70b05
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501637"
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, explizit anzufordern, dass die Common Language Runtime (CLR) eine neue Aufgabe erstellen, die aktuell ausgeführte Aufgabe erhalten und die geografische Sprache und Kultur für den Task festlegen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CreateTask-Methode](iclrtaskmanager-createtask-method.md)|Fordert explizit an, dass die CLR eine neue [ICLRTask](iclrtask-interface.md) -Instanz erstellt.|  
|[GetCurrentTask-Methode](iclrtaskmanager-getcurrenttask-method.md)|Ruft die- `ICLRTask` Instanz ab, die den derzeit ausgeführten Task darstellt.|  
|[GetCurrentTaskType-Methode](iclrtaskmanager-getcurrenttasktype-method.md)|Ruft den Typ der Aufgabe ab, die gerade ausgeführt wird.|  
|[SetLocale-Methode](iclrtaskmanager-setlocale-method.md)|Benachrichtigt die CLR, dass der Host den Gebiets Schema Bezeichner für die aktuell ausgeführte Aufgabe geändert hat.|  
|[SetUILocale-Methode](iclrtaskmanager-setuilocale-method.md)|Benachrichtigt den Common Language Runtime, dass der Host den Gebiets Schema Bezeichner für die Benutzeroberfläche für den aktuell ausgeführten Task geändert hat.|  
  
## <a name="remarks"></a>Bemerkungen  
 Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird, verfügt über Darstellungen sowohl auf der Host Seite (eine Instanz von [IHostTask](ihosttask-interface.md)) als auch auf der CLR-Seite (eine Instanz von [ICLRTask](iclrtask-interface.md)). Entweder der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die Host seitige Darstellung muss einer entsprechenden CLR-seitigen Darstellung zugeordnet sein, um eine erfolgreiche Kommunikation zwischen dem Host und der CLR bezüglich der Aufgabe sicherzustellen. Die beiden Objekte müssen erstellt und instanziiert werden, bevor verwalteter Code in einem Betriebssystem Thread ausgeführt werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
