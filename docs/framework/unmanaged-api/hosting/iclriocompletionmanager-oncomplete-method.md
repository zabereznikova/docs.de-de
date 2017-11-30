---
title: ICLRIoCompletionManager::OnComplete-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd38679d1b8d099e5eb6330e03e2333b03780dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete-Methode
Benachrichtigt die common Language Runtime (CLR) über den Status einer e/a-Anforderung, die erstellt wurde, mithilfe eines Aufrufs an die [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwErrorCode`  
 [in] Ein HRESULT-Wert, der den Status des Bindungsvorgangs angibt.  
  
-   S_OK gibt an, dass der Vorgang erfolgreich abgeschlossen.  
  
-   HOST_E_INTERRUPTED gibt an, dass der Aufruf verfrüht beendet.  
  
-   E_FAIL gibt an, dass ein Unbekannter, nicht mehr wiederherstellbar, schwerwiegender Fehler aufgetreten ist.  
  
 `NumberOfBytesTransferred`  
 [in] Die Anzahl der Bytes während der Verarbeitung der e/a-Anforderung übertragen.  
  
 `pvOverlapped`  
 [in] Ein Zeiger auf die `OVERLAPPED` -Struktur, die für den Aufruf übergeben wurde die `IHostIoCompletionManager::Bind` Methode.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OnComplete`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Host eine e/a-Abschluss-Abstraktion implementiert, macht die CLR e/a-Anforderungen über den Host mithilfe der Methoden der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md). Der Host ruft dann die `OnComplete` Methode, um die Laufzeit über das Ergebnis des solche Anforderungen darüber zu informieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
