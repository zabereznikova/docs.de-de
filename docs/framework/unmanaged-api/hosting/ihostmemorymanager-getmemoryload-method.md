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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176278"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad-Methode
Ruft den physischen Speicher ab, der derzeit verwendet wird und daher nicht verfügbar ist, wie vom Host gemeldet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pMemoryLoad`  
 [out] Ein Zeiger auf den ungefähren Prozentsatz des gesamten physischen Speichers, der derzeit verwendet wird.  
  
 `pAvailableBytes`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die für die Common Language Runtime (CLR) verfügbar sind.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`erfolgreich zurückgegeben werden.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Bemerkungen  
 `GetMemoryLoad`umschließt die Win32-Funktion. `GlobalMemoryStatus` Der Wert `pMemoryLoad` von ist `dwMemoryLoad` das Äquivalent `MEMORYSTATUS` des `GlobalMemoryStatus`Felds in der Struktur, die von zurückgegeben wird.  
  
 Die Laufzeit verwendet den Rückgabewert als Heuristik für den Garbage Collector. Wenn der Host beispielsweise meldet, dass der Großteil des Speichers verwendet wird, kann der Garbage Collector aus mehreren Generationen sammeln, um die Speichermenge zu erhöhen, die möglicherweise verfügbar werden kann.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
