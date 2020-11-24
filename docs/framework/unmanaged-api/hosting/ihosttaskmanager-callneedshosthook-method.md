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
ms.openlocfilehash: 7c7af1bbf3d13c3f66d525dfce69d8b49fbe045c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675138"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook-Methode

Ermöglicht dem Host, anzugeben, ob die Common Language Runtime (CLR) den angegebenen aufrufenden Befehl an eine nicht verwaltete Funktion Inline bereitstellen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `target`  
 in Die Adresse in der zugeordneten PE-Datei (portable ausführbare Datei) der nicht verwalteten Funktion, die aufgerufen werden soll.  
  
 `pbCallNeedsHostHook`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob der Host den aufzurufenden-aufzurufenden erfordert.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Um die Codeausführung zu optimieren, führt die CLR während der Kompilierung eine Analyse der einzelnen Platt Form Aufrufe durch, um zu bestimmen, ob der Aufruf Inline sein kann. `CallNeedsHostHook` ermöglicht es dem Host, diese Entscheidung zu überschreiben, indem gefordert wird, dass ein aufzurufende nicht verwaltete Funktion eingebunden wird. Wenn der Host einen Hook erfordert, wird der-Befehl von der Laufzeit nicht Inline aufgerufen.  
  
 Der Host erfordert in der Regel einen Hook, bei dem ein Gleit Komma Zustand angepasst werden muss, oder nach dem Empfang einer Benachrichtigung, dass ein-Befehl in einen Zustand versetzt wird, in dem der Host die Anforderungen für den Arbeitsspeicher oder die erforderlichen Sperren der Laufzeit nicht nachverfolgen kann. Wenn der Host erfordert, dass der Aufruf eingebunden ist, benachrichtigt die Common Language Runtime den Host über Übergänge zum und von verwaltetem Code mithilfe von Aufrufen von " [deterruntime](ihosttaskmanager-enterruntime-method.md)", " [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md)", " [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)" und " [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)".  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
