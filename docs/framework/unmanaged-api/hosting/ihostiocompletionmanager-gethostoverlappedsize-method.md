---
title: IHostIoCompletionManager::GetHostOverlappedSize-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
ms.openlocfilehash: a97009a4ebc834d867dddcc350033c550364ea42
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804751"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>IHostIoCompletionManager::GetHostOverlappedSize-Methode
Ruft die Größe aller benutzerdefinierten Daten ab, die der Host an e/a-Anforderungen anfügen soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pcbSize`  
 vorgenommen Ein Zeiger auf die Anzahl der Bytes, die der Common Language Runtime (CLR) zusätzlich zur Größe des Win32-Objekts zuordnen soll `OVERLAPPED` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Alle asynchronen e/a-Aufrufe an Windows-Plattform-APIs nehmen ein Win32- `OVERLAPPED` Objekt an, das Informationen wie die Dateizeiger Position bereitstellt. Zur Aufrechterhaltung des Zustands fügen Anwendungen, die asynchrone e/a-Aufrufe durchführen, in der Regel benutzerdefinierte Daten zur Struktur hinzu. `GetHostOverlappedSize`und [IHostIoCompletionManager:: initializehostoverllapp](ihostiocompletionmanager-initializehostoverlapped-method.md) bieten dem Host die Möglichkeit, solche benutzerdefinierten Daten einzuschließen.  
  
 Die CLR ruft die- `GetHostOverlappedSize` Methode auf, um die Größe der benutzerdefinierten Daten zu bestimmen, die der Host an das-Objekt anfügen soll `OVERLAPPED` .  
  
> [!NOTE]
> `GetHostOverlappedSize`wird nur einmal aufgerufen. Die benutzerdefinierten Daten des Hosts müssen für jede e/a-Anforderung dieselbe Größe aufweisen.  
  
> [!IMPORTANT]
> Die Größe des `OVERLAPPED` Objekts selbst ist nicht im Wert von enthalten `pcbSize` .  
  
 Weitere Informationen zur `OVERLAPPED` Struktur finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.NativeOverlapped>
- [ICLRIoCompletionManager-Schnittstelle](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)
