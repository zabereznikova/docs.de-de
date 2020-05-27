---
title: IHostThreadPoolManager::GetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842282"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>IHostThreadPoolManager::GetMaxThreads-Methode
Ruft die maximale Anzahl von Threads ab, die der Host gleichzeitig im Thread Pool verwaltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwMaxWorkerThreads`  
 vorgenommen Ein Zeiger auf die maximale Anzahl von Threads, die der Host im Thread Pool verwaltet.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die Common Language Runtime (CLR () wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_NOTIMPL|Der Host stellt keine Implementierung von bereit `GetMaxThreads` .|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR ruft `GetMaxThreads` auf, um die Gesamtanzahl der Threads im Thread Pool zu bestimmen. Die [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) -Methode ruft die Anzahl der Threads ab, die derzeit keine Arbeitselemente verarbeiten. Alle Anforderungen oberhalb des zurückgegebenen Werts des- `pdwMaxWorkerThreads` Parameters bleiben in der Warteschlange, bis die Threads verfügbar werden.  
  
 Wenn der Host keine Implementierung von bereitstellt `GetMaxThreads` , sollte er den HRESULT-Wert E_NOTIMPL zurückgeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [GetMinThreads-Methode](ihostthreadpoolmanager-getminthreads-method.md)
- [SetMaxThreads-Methode](ihostthreadpoolmanager-setmaxthreads-method.md)
- [IHostThreadPoolManager-Schnittstelle](ihostthreadpoolmanager-interface.md)
