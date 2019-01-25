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
ms.openlocfilehash: bb91c5dfbe5c83e08d786043d7e4732fa19e53db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566784"
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
 [in] Die Adresse in der Datei zugeordneten PE (portable Executable), der nicht verwaltete Funktion, die aufgerufen werden soll.  
  
 `pbCallNeedsHostHook`  
 [out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Host den Aufruf von verknüpft werden muss.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Optimieren der Ausführung von Code führt die CLR eine Analyse der einzelnen Plattformen Plattformaufrufs während der Kompilierung, um festzustellen, ob der Aufruf als Inlinefunktion umgesetzt werden kann. `CallNeedsHostHook` kann der Host dieser Entscheidung zu überschreiben, indem Sie festlegen, dass ein Aufruf an eine nicht verwaltete Funktion verknüpft werden. Wenn der Host einen Hook erforderlich ist, kann die Laufzeit den Aufruf nicht Inline.  
  
 Der Host benötigt in der Regel einen Hook, an der sie eine Gleitkommazustand anpassen muss, oder nach dem Empfang der Benachrichtigung, dass ein Aufruf einen Status übergeht, in dem der Host der Common Language Runtime-Anforderungen für Speicher oder alle Sperren nachverfolgt werden können. Wenn der Host erfordert, dass der Aufruf verknüpft werden, benachrichtigt die Laufzeit den Host der Übergänge in und aus verwaltetem Code, durch Aufrufe [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), und [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
