---
title: ICLRTask2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8701cff3400e46660fac90486cf5648d29aa9972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2-interface"></a>ICLRTask2-Schnittstelle
Stellt die Funktionalität von der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Schnittstelle; darüber hinaus bietet Methoden, die es ermöglichen, Thread-Abbrüche um für den aktuellen Thread verzögert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginPreventAsyncAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Neuer Thread Verzögerungen Abbrechen Anforderungen für den aktuellen Thread.|  
|[EndPreventAsyncAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Ermöglicht, dass neue oder ausstehende Thread Abort Anforderungen zu Thread führt bricht ab, für den aktuellen Thread.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICLRTask2` Schnittstelle erbt die `ICLRTask` Schnittstelle und fügt Methoden, mit denen den Host zu verzögern, Threadabbrüche, um einen Bereich von Code zu schützen, die nicht fehlschlagen darf. Aufrufen von `BeginPreventAsyncAbort` erhöht den Zähler Verzögerung Threadabbruchs für den aktuellen Thread, und der Aufruf `EndPreventAsyncAbort` verringert es. Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` können geschachtelt sein. Solange der Leistungsindikator größer als 0 (null) ist, werden Threadabbrüche für den aktuellen Thread verzögert.  
  
 Wenn Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` werden nicht paarweise zugeordnet, es ist möglich, einen Status erreichen, in welchem Thread Threadabbrüche für den aktuellen Thread nicht übermittelt werden.  
  
 Die Verzögerung wird für einen Thread, der selbst abbricht, nicht berücksichtigt.  
  
 Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet. Missbrauch dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer. Beispielsweise Aufrufen `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn der virtuellen Computer zuvor erhöht wurde. Auf ähnliche Weise wird der interne Zähler auf Überläufe nicht überprüft. Wenn er ganzzahlige Limit überschreitet, da er vom Host und dem virtuellen Computer erhöht wird, ist das resultierende Verhalten nicht angegeben.  
  
 Für Informationen zu Elementen geerbt `ICLRTask` und zu anderen Verwendungsmöglichkeiten dieser Schnittstelle finden Sie unter der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
