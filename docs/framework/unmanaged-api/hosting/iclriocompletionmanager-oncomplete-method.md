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
ms.openlocfilehash: 39c9752912e88b04455516c0e9bed43610ba8aa0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703811"
---
# <a name="iclriocompletionmanageroncomplete-method"></a>ICLRIoCompletionManager::OnComplete-Methode
Benachrichtigt den Common Language Runtime (CLR) über den Status einer e/a-Anforderung, die mithilfe eines Aufrufes der [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) -Methode durchgeführt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwErrorCode`  
 in Ein HRESULT-Wert, der den Status des Bindungs Vorgangs angibt.  
  
- S_OK gibt an, dass der Vorgang erfolgreich abgeschlossen wurde.  
  
- HOST_E_INTERRUPTED gibt an, dass der-Rückruf vor dem Abschluss beendet wurde.  
  
- E_FAIL gibt an, dass ein unbekannter, nicht BEHEB barer, schwerwiegender Fehler aufgetreten ist.  
  
 `NumberOfBytesTransferred`  
 in Die Anzahl von Bytes, die während der Verarbeitung der e/a-Anforderung übertragen wurden.  
  
 `pvOverlapped`  
 in Ein Zeiger auf die- `OVERLAPPED` Struktur, die an den-aufrufbefehl an die-Methode übermittelt wurde `IHostIoCompletionManager::Bind` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`OnComplete`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Host eine e/a-Abschluss Abstraktion implementiert, stellt die CLR e/a-Anforderungen über den Host mithilfe von [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)-Methoden her. Der Host ruft dann die- `OnComplete` Methode auf, um die Laufzeit über das Ergebnis solcher Anforderungen zu benachrichtigen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRIoCompletionManager-Schnittstelle](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager-Schnittstelle](ihostthreadpoolmanager-interface.md)
