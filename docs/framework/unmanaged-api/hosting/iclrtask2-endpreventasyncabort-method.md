---
title: ICLRTask2::EndPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 7f8963403c60815bbf1cd3008ed7fec73d849fea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720255"
---
# <a name="iclrtask2endpreventasyncabort-method"></a>ICLRTask2::EndPreventAsyncAbort-Methode

Ermöglicht es, dass neue oder ausstehende Thread Abbruch Anforderungen dazu führen, dass Threads im aktuellen Thread abgebrochen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_INVALIDOPERATION|Die-Methode wurde für einen Thread aufgerufen, der nicht der aktuelle Thread ist.|  
  
## <a name="remarks"></a>Hinweise  

 Durch den Aufruf dieser Methode wird der Delay-Thread-Abort-Leistungswert für den aktuellen Thread um 1 verringert.  
  
 Aufrufe von [ICLRTask2:: BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) und `EndPreventAsyncAbort` können eingebettet werden. Solange der Leistungswert größer als 0 (null) ist, werden Thread Abbrüche für den aktuellen Thread verzögert.  
  
 Die Funktionalität, die von diesem Feature verfügbar gemacht wird, wird intern vom virtuellen Computer (VM) verwendet. Der Missbrauch dieser Methoden kann zu einem nicht angegebenen Verhalten auf dem virtuellen Computer führen. `EndPreventAsyncAbort`Wenn Sie z. b. aufrufen, ohne zuerst aufrufen, `BeginPreventAsyncAbort` können Sie den-Wert auf Null setzen, wenn der virtuelle Computer ihn zuvor erhöht hat. Auf ähnliche Weise wird der interne Counter nicht auf einen Überlauf geprüft. Wenn Sie die ganzzahlige Beschränkung überschreitet, weil Sie sowohl vom Host als auch vom virtuellen Computer inkrementiert wird, ist das resultierende Verhalten nicht angegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [BeginPreventAsyncAbort-Methode](iclrtask2-beginpreventasyncabort-method.md)
- [ICLRTask2-Schnittstelle](iclrtask2-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
