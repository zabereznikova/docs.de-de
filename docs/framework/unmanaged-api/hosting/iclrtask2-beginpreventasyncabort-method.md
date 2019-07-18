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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23ead080823ace1b091568108af8866dcbca14ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770265"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>ICLRTask2::BeginPreventAsyncAbort-Methode
Verzögerungen bei der neuer Thread abgebrochen werden Anforderungen von Threadabbrüche für den aktuellen Thread führt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_INVALIDOPERATION|Die Methode wurde in einem Thread aufgerufen, die nicht der aktuelle Thread ist.|  
  
## <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Methode wird die Verzögerung Threadabbruchs Leistungsindikator für den aktuellen Thread um eins inkrementiert.  
  
 Aufrufe von `BeginPreventAsyncAbort` und [ICLRTask2:: EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) können geschachtelt werden. Solange der Zähler größer als 0 (null) ist, verzögert Threadabbrüche für den aktuellen Thread werden. Wenn dieser Aufruf mit einem Aufruf von nicht paarweise angegeben, wird die `EndPreventAsyncAbort` -Methode, es ist möglich, einen Zustand zu erreichen, in welchem Thread Threadabbrüche für den aktuellen Thread nicht übermittelt werden.  
  
 Die Verzögerung wird für einen Thread, der selbst abbricht, nicht berücksichtigt.  
  
 Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet. Falsche Verwendung dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer. Zum Beispiel der Aufruf `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn es zuvor von der virtuellen Computer erhöht wurde. Auf ähnliche Weise wird der interne Zähler nicht auf Überläufe überprüft. Wenn es die ganzzahligen Grenzwert überschreitet, da er sowohl auf dem Host und auf dem virtuellen Computer um eins erhöht wird, ist das resultierende Verhalten nicht angegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EndPreventAsyncAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
