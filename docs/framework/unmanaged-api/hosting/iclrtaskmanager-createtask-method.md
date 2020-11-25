---
title: ICLRTaskManager::CreateTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: c8d18b78cf0185271eae763892610d13f76e42ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733996"
---
# <a name="iclrtaskmanagercreatetask-method"></a>ICLRTaskManager::CreateTask-Methode

Fordert explizit an, dass die Common Language Runtime (CLR) eine neue Aufgabe erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pTask`  
 vorgenommen Ein Zeiger auf die Adresse eines neu erstellten [ICLRTask](iclrtask-interface.md)-Element oder NULL, wenn die Aufgabe nicht erstellt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  

 Die CLR erstellt bei der Initialisierung automatisch eine neue Aufgabe, wenn Benutzercode einen Thread mithilfe von Typen im- <xref:System.Threading> Namespace oder durch Erhöhen der Größe des Thread Pools erstellt. Außerdem werden Aufgaben erstellt, wenn von nicht verwaltetem Code eine verwaltete Funktion aufgerufen wird.  
  
 `CreateTask` ermöglicht dem Host, eine explizite Anforderung zu erstellen, dass die CLR eine neue Aufgabe erstellt. Beispielsweise kann der Host diese Methode aufrufen, um Datenstrukturen vorab zu initialisieren.  
  
> [!IMPORTANT]
> Die neue Aufgabe wird in einem angehaltenen Zustand zurückgegeben und bleibt angehalten, bis der Host [IHostTask:: Start](ihosttask-start-method.md)explizit aufruft.  
  
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
