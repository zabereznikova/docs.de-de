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
ms.openlocfilehash: 68a9d6ad7470ffaf1143a4a8e3134f20edb9e3c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439217"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery-Methode
Dient als logischer Wrapper für die entsprechenden Win32-Funktion. Die Win32-Implementierung von `VirtualQuery` Ruft Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `lpAddress`  
 [in] Ein Zeiger auf die Adresse im virtuellen Arbeitsspeicher, der abgefragt werden.  
  
 `lpBuffer`  
 [out] Ein Zeiger auf eine Struktur, die Informationen über den angegebenen Speicherbereich enthält.  
  
 `dwLength`  
 [in] Die Größe des Puffers in Bytes, die `lpBuffer` verweist auf.  
  
 `pResult`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die vom Informationspuffer zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `VirtualQuery` enthält Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses. Diese Implementierung legt den Wert für die `pResult` Parameter, um die Anzahl der Bytes im Informationspuffer zurückgegeben, und gibt einen HRESULT-Wert zurück. In der Win32- `VirtualQuery` -Funktion, der Rückgabewert ist die Größe des Puffers. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
> [!IMPORTANT]
>  Das Betriebssystem-Implementierung von `VirtualQuery` tritt kein Deadlock und bis Abschluss mit zufällig angehaltenen Threads im Benutzercode ausgeführt werden kann. Seien Sie äußerst vorsichtig, wenn Sie eine gehostete Version dieser Methode zu implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
