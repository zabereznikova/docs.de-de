---
title: IHostMemoryManager::VirtualQuery-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e18c035060b8d5b38649011597d35d75fa2d8ef
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497183"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery-Methode
Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion. Die Win32-Implementierung von `VirtualQuery` Ruft Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lpAddress`  
 [in] Ein Zeiger auf die Adresse im virtuellen Speicher abgefragt werden.  
  
 `lpBuffer`  
 [out] Ein Zeiger auf eine Struktur, die Informationen über den angegebenen Speicherbereich enthält.  
  
 `dwLength`  
 [in] Die Größe des Puffers in Bytes, die `lpBuffer` verweist auf.  
  
 `pResult`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die vom Informationspuffer zurückgegeben werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `VirtualQuery` enthält Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses. Diese Implementierung legt den Wert für die `pResult` Parameter, um die Anzahl der Bytes im Informationspuffer zurückgegeben, und gibt einen HRESULT-Wert zurück. In der Win32- `VirtualQuery` -Funktion, der Rückgabewert ist die Größe des Puffers. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
> [!IMPORTANT]
>  Implementierung des Betriebssystems `VirtualQuery` tritt kein Deadlock und kann mit zufällig im Benutzercode angehaltenen Threads bis zum Abschluss ausgeführt. Seien Sie äußerst vorsichtig, wenn Sie eine gehostete Version dieser Methode zu implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
