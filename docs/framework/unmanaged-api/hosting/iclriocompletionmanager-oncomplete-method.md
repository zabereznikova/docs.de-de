---
title: ICLRIoCompletionManager::OnComplete-Methode
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f2df623f9d191899390456a20e84a88f06f0b49
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592846"
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete-Methode
Benachrichtigt Sie die common Language Runtime (CLR) über den Status einer e/a-Anforderung, die erstellt wurde, mithilfe eines Aufrufs an die [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwErrorCode`  
 [in] Ein HRESULT-Wert, der den Status des Bindevorgangs angibt.  
  
- S_OK gibt an, dass der Vorgang erfolgreich abgeschlossen.  
  
- HOST_E_INTERRUPTED gibt an, dass der Aufruf vor dem Abschluss beendet.  
  
- E_FAIL gibt an, dass ein Unbekannter, nicht mehr wiederherstellbar, schwerwiegender Fehler ist aufgetreten.  
  
 `NumberOfBytesTransferred`  
 [in] Die Anzahl der Bytes während der Verarbeitung der e/a-Anforderung übertragen.  
  
 `pvOverlapped`  
 [in] Ein Zeiger auf die `OVERLAPPED` -Struktur, die an den Aufruf übergeben wurde die `IHostIoCompletionManager::Bind` Methode.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OnComplete` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Host eine e/a-Abschluss-Abstraktion implementiert, die CLR kann e/a-Anforderungen über den Host mithilfe der Methoden der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md). Der Host ruft dann die `OnComplete` -Methode benachrichtigt die Laufzeit über das Ergebnis des solche Anforderungen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
