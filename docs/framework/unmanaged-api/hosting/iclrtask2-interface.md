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
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124523"
---
# <a name="iclrtask2-interface"></a>ICLRTask2-Schnittstelle
Stellt die gesamte Funktionalität der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Schnittstelle bereit. Außerdem stellt Methoden bereit, mit denen Thread Abbrüche im aktuellen Thread verzögert werden können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginPreventAsyncAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Verzögert neue Thread Abbruch Anforderungen für den aktuellen Thread.|  
|[EndPreventAsyncAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Ermöglicht es, dass neue oder ausstehende Thread Abbruch Anforderungen dazu führen, dass Threads im aktuellen Thread abgebrochen werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICLRTask2`-Schnittstelle erbt die `ICLRTask`-Schnittstelle und fügt Methoden hinzu, mit denen der Host Thread Abbrüche verzögern kann, um einen Code Bereich zu schützen, der nicht fehlschlagen darf. Durch Aufrufen von `BeginPreventAsyncAbort` wird der Delay-Thread-Abort-Leistungswert für den aktuellen Thread erhöht, und der Aufruf von `EndPreventAsyncAbort` Dekremente ihn. Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` können eingebettet werden. Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.  
  
 Wenn Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` nicht gekoppelt sind, ist es möglich, einen Zustand zu erreichen, in dem Thread Abbrüche nicht an den aktuellen Thread übermittelt werden können.  
  
 Die Verzögerung wird für einen Thread, der sich selbst abbricht, nicht berücksichtigt.  
  
 Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet. Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen. Wenn Sie z. b. `EndPreventAsyncAbort` aufrufen, ohne zuerst `BeginPreventAsyncAbort` aufrufen, können Sie den-Wert auf NULL festlegen, wenn der virtuelle Computer ihn zuvor erhöht hat. Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft. Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.  
  
 Informationen zu Membern, die von `ICLRTask` geerbt werden, sowie zu den anderen Verwendungsmöglichkeiten dieser Schnittstelle finden Sie in der [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
