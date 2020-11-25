---
title: ICLRTask2::BeginPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: daf211fcc496f63ef71575abf6a28655004db264
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720242"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>ICLRTask2::BeginPreventAsyncAbort-Methode

Verzögert neue Thread Abbruch Anforderungen, was dazu führt, dass Threads im aktuellen Thread abgebrochen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_INVALIDOPERATION|Die-Methode wurde für einen Thread aufgerufen, der nicht der aktuelle Thread ist.|  
  
## <a name="remarks"></a>Hinweise  

 Durch den Aufruf dieser Methode wird der Delay-Thread-Abbruch-Leistungswert für den aktuellen Thread um 1 erhöht.  
  
 Aufrufe von `BeginPreventAsyncAbort` und [ICLRTask2:: EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) können nicht eingefügt werden. Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert. Wenn dieser-Befehl nicht mit einem Aufrufen der-Methode gekoppelt ist `EndPreventAsyncAbort` , kann ein Zustand erreicht werden, in dem Thread Abbrüche nicht an den aktuellen Thread übermittelt werden können.  
  
 Die Verzögerung wird für einen Thread, der sich selbst abbricht, nicht berücksichtigt.  
  
 Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet. Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen. `EndPreventAsyncAbort`Wenn Sie z. b. aufrufen, ohne zuerst aufrufen, `BeginPreventAsyncAbort` können Sie den-Wert auf Null setzen, wenn der virtuelle Computer ihn zuvor erhöht hat. Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft. Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EndPreventAsyncAbort-Methode](iclrtask2-endpreventasyncabort-method.md)
- [ICLRTask2-Schnittstelle](iclrtask2-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
