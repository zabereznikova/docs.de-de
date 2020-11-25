---
title: IHostMemoryManager::GetMemoryLoad-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 0611b82e22ec9d5d2cde2a7f46e65b5e25733610
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731357"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad-Methode

Ruft die Menge des physischen Speichers ab, der zurzeit verwendet wird und daher nicht verfügbar ist, wie vom Host gemeldet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pMemoryLoad`  
 vorgenommen Ein Zeiger auf den ungefähren Prozentsatz des gesamten physischen Speichers, der zurzeit verwendet wird.  
  
 `pAvailableBytes`  
 vorgenommen Ein Zeiger auf die Anzahl der Bytes, die für die Common Language Runtime (CLR) verfügbar sind.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 `GetMemoryLoad` umschließt die Win32- `GlobalMemoryStatus` Funktion. Der Wert von `pMemoryLoad` ist die Entsprechung des- `dwMemoryLoad` Felds in der-Struktur, die `MEMORYSTATUS` von zurückgegeben wird `GlobalMemoryStatus` .  
  
 Die Laufzeit verwendet den Rückgabewert als heuristisch für die Garbage Collector. Wenn der Host z. b. meldet, dass der größte Teil des Arbeitsspeichers verwendet wird, kann der Garbage Collector die Erfassung aus mehreren Generierungen wählen, um die Menge an Arbeitsspeicher zu erhöhen, die potenziell verfügbar werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
