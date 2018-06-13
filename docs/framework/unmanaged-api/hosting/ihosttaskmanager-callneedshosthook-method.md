---
title: IHostTaskManager::CallNeedsHostHook-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 983cad5ed87d0666ed71a805a3b3f7a3c7e7c091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444303"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook-Methode
Ermöglicht es dem Host anzugeben, ob die common Language Runtime (CLR) kann den angegebenen Aufruf an eine nicht verwaltete Funktion Inline aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `target`  
 [in] Die Adresse innerhalb der zugeordneten PE (portable Executable)-Datei, die nicht verwaltete Funktion, die aufgerufen werden soll.  
  
 `pbCallNeedsHostHook`  
 [out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Host den Aufruf eingebunden werden muss.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Optimieren der Ausführung von Code führt die CLR eine Analyse jeder Plattform Plattformaufrufs während der Kompilierung, um zu bestimmen, ob der Aufruf inline gesetzt werden kann. `CallNeedsHostHook` mit der Host dieser Entscheidung zu überschreiben, indem Sie festlegen, dass ein Aufruf an eine nicht verwaltete Funktion verknüpft werden kann. Wenn der Host einen Hook erforderlich ist, kann die Laufzeit den Aufruf nicht Inline.  
  
 Der Host in der Regel einen Hook, müsste ein Gleitkommazustand angepasst werden muss oder nach dem Empfang der Benachrichtigung, dass ein Aufruf einen Zustand eintritt, in dem der Host die Common Language Runtime-Anforderungen für Arbeitsspeicher oder alle Sperren nachverfolgt werden können. Wenn der Host erfordert, dass der Aufruf verknüpft werden, benachrichtigt die Laufzeit den Host der Übergänge in und aus verwaltetem Code durch Aufrufe [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), und [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
