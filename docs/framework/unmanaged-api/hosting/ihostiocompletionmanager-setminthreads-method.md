---
title: IHostIoCompletionManager::SetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: 29a2fc5652badcc00378192debccba0356f5339e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804655"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a>IHostIoCompletionManager::SetMinThreads-Methode
Legt die Mindestanzahl von Threads fest, die der Host für die e/a-Vervollständigung in hohem Maß beachten soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwMinIoCompletionThreads`  
 in Die Mindestanzahl von e/a-Abschluss-Threads, die der Host erstellen soll.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetMinThreads`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_NOTIMPL|Der Host stellt keine Implementierung von bereit `SetMinThreads` .|  
  
## <a name="remarks"></a>Hinweise  
 Ein Host möchte möglicherweise eine exklusive Kontrolle über die Anzahl der Threads, die für die Verarbeitung von e/a-Anforderungen zugewiesen werden können, z. b. die Implementierung, die Leistung oder die Skalierbarkeit. Aus diesem Grund ist es nicht erforderlich, dass der Host implementiert `SetMinThreads` . In diesem Fall sollte der Host E_NOTIMPL aus dieser Methode zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRIoCompletionManager-Schnittstelle](iclriocompletionmanager-interface.md)
- [SetMaxThreads-Methode](ihostiocompletionmanager-setmaxthreads-method.md)
- [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)
