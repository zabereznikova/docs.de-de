---
title: IHostSecurityManager::SetSecurityContext-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 6a6b4d0351e22026dc873aad8281d0259d871a14
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501481"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>IHostSecurityManager::SetSecurityContext-Methode
Legt den Sicherheitskontext des aktuell ausgeführten Threads fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `eContextType`  
 in Einer der [EContextType](econtexttype-enumeration.md) -Werte, der angibt, welche Art von Kontext die Common Language Runtime (CLR) auf dem Host platziert.  
  
 `ppSecurityContext`  
 vorgenommen Ein Zeiger auf die Adresse eines neuen [IHostSecurityContext](ihostsecuritycontext-interface.md) -Objekts.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die CLR ruft `SetSecurityContext` in verschiedenen Szenarien auf. Bevor Klassen-und Modulkonstruktoren und Finalizer ausgeführt werden, ruft die CLR `SetSecurityContext` auf, um den Host vor Ausführungsfehlern zu schützen. Anschließend wird der Sicherheitskontext nach der Ausführung des Konstruktors oder Finalizers mithilfe eines anderen Aufrufes wieder auf den ursprünglichen Zustand zurückgesetzt `SetSecurityContext` . Ein ähnliches Muster tritt bei der e/a-Vervollständigung auf. Wenn der Host [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)implementiert, ruft die CLR auf, `SetSecurityContext` nachdem der Host [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)aufgerufen hat.  
  
 Bei asynchronen Punkten in Arbeitsthreads ruft die CLR `SetSecurityContext` innerhalb von <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> oder innerhalb von [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)auf, je nachdem, ob der Host oder die CLR den Thread Pool implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [EContextType-Enumeration](econtexttype-enumeration.md)
- [ICLRIoCompletionManager-Schnittstelle](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)
- [IHostSecurityContext-Schnittstelle](ihostsecuritycontext-interface.md)
- [IHostSecurityManager-Schnittstelle](ihostsecuritymanager-interface.md)
- [IHostThreadPoolManager-Schnittstelle](ihostthreadpoolmanager-interface.md)
