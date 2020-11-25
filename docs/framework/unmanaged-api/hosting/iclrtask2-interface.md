---
title: ICLRTask2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 9332b3462ba389783a113d173e32850d40427ce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720229"
---
# <a name="iclrtask2-interface"></a>ICLRTask2-Schnittstelle

Stellt die gesamte Funktionalität der [ICLRTask](iclrtask-interface.md) -Schnittstelle bereit. Außerdem stellt Methoden bereit, mit denen Thread Abbrüche im aktuellen Thread verzögert werden können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[BeginPreventAsyncAbort-Methode](iclrtask2-beginpreventasyncabort-method.md)|Verzögert neue Thread Abbruch Anforderungen für den aktuellen Thread.|  
|[EndPreventAsyncAbort-Methode](iclrtask2-endpreventasyncabort-method.md)|Ermöglicht es, dass neue oder ausstehende Thread Abbruch Anforderungen dazu führen, dass Threads im aktuellen Thread abgebrochen werden.|  
  
## <a name="remarks"></a>Hinweise  

 Die `ICLRTask2` -Schnittstelle erbt die `ICLRTask` -Schnittstelle und fügt Methoden hinzu, die es dem Host ermöglichen, Thread Abbrüche zu verzögern, um einen Code Bereich zu schützen, der nicht fehlschlagen darf. Durch Aufrufen `BeginPreventAsyncAbort` von wird der Delay-Thread-Abort-Leistungswert für den aktuellen Thread Inkrementen erhöht, und der Aufruf verringert `EndPreventAsyncAbort` ihn. Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` können eingebettet werden. Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.  
  
 Wenn Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` nicht gekoppelt sind, kann ein Zustand erreicht werden, in dem Thread Abbrüche nicht an den aktuellen Thread übermittelt werden können.  
  
 Die Verzögerung wird für einen Thread, der sich selbst abbricht, nicht berücksichtigt.  
  
 Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet. Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen. `EndPreventAsyncAbort`Wenn Sie z. b. aufrufen, ohne zuerst aufrufen, `BeginPreventAsyncAbort` können Sie den-Wert auf Null setzen, wenn der virtuelle Computer ihn zuvor erhöht hat. Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft. Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.  
  
 Informationen zu Membern `ICLRTask` , die von und zu den anderen Verwendungsmöglichkeiten dieser Schnittstelle geerbt werden, finden Sie in der [ICLRTask](iclrtask-interface.md) -Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
