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
ms.openlocfilehash: 6e3cb5bcec831f143d45f733c9e2f977390aade6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731240"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery-Methode

Dient als logischer Wrapper für die entsprechende Win32-Funktion. Die Win32-Implementierung von `VirtualQuery` Ruft Informationen zu einem Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `lpAddress`  
 in Ein Zeiger auf die Adresse im virtuellen Speicher, die abgefragt werden soll.  
  
 `lpBuffer`  
 vorgenommen Ein Zeiger auf eine-Struktur, die Informationen über den angegebenen Speicherbereich enthält.  
  
 `dwLength`  
 in Die Größe (in Bytes) des Puffers, `lpBuffer` auf den verweist.  
  
 `pResult`  
 vorgenommen Ein Zeiger auf die Anzahl der vom Informations Puffer zurückgegebenen Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 `VirtualQuery` stellt Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses bereit. Diese Implementierung legt den Wert des- `pResult` Parameters auf die Anzahl der im Informations Puffer zurückgegebenen Bytes fest und gibt einen HRESULT-Wert zurück. In der Win32- `VirtualQuery` Funktion ist der Rückgabewert die Puffergröße. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
> [!IMPORTANT]
> Die Implementierung von des Betriebssystems `VirtualQuery` führt nicht zu einem Deadlock und kann mit zufälligen Threads ausgeführt werden, die im Benutzercode angehalten werden. Gehen Sie bei der Implementierung einer gehosteten Version dieser Methode sehr vorsichtig vor.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
