---
title: IHostIoCompletionManager::InitializeHostOverlapped-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: cf257ab86d27946c861c89dff5e6f09a42013e58
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804716"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>IHostIoCompletionManager::InitializeHostOverlapped-Methode
Bietet dem Host die Möglichkeit, benutzerdefinierte Daten zu initialisieren, um Sie an eine Win32-Struktur anzufügen `OVERLAPPED` , die für asynchrone e/a-Anforderungen verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pvOverlapped`  
 in Ein Zeiger auf die Win32- `OVERLAPPED` Struktur, die in der e/a-Anforderung enthalten sein soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Die Funktionen der Windows-Plattform verwenden die- `OVERLAPPED` Struktur, um den Zustand für asynchrone e/a-Anforderungen zu speichern. Die CLR ruft die- `InitializeHostOverlapped` Methode auf, um dem Host die Möglichkeit zu geben, benutzerdefinierte Daten an eine Instanz anzufügen `OVERLAPPED` .  
  
> [!IMPORTANT]
> Um zum Anfang des benutzerdefinierten Datenblocks zu gelangen, müssen die Hosts den Offset auf die Größe der `OVERLAPPED` Struktur ( `sizeof(OVERLAPPED)` ) festlegen.  
  
 Der Rückgabewert E_OUTOFMEMORY gibt an, dass der Host seine benutzerdefinierten Daten nicht initialisieren konnte. In diesem Fall meldet die CLR einen Fehler und schlägt den-Befehl fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRIoCompletionManager-Schnittstelle](iclriocompletionmanager-interface.md)
- [GetHostOverlappedSize-Methode](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)
