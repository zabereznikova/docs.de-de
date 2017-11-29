---
title: IHostMemoryManager::GetMemoryLoad-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.GetMemoryLoad
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7296790eb80fe90cd115150749e533ce1800834b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad-Methode
Ruft die Größe des physischen Speichers, der zurzeit verwendet wird und daher nicht verfügbar ist, von dem Host gemeldet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMemoryLoad`  
 [out] Ein Zeiger auf den ungefähren Prozentsatz des gesamten physischen Arbeitsspeichers, die derzeit verwendet wird.  
  
 `pAvailableBytes`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die für die common Language Runtime (CLR) verfügbar.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `GetMemoryLoad`Dient als Wrapper für Win32 `GlobalMemoryStatus` Funktion. Den Wert der `pMemoryLoad` ist das Äquivalent der `dwMemoryLoad` -Feld in der `MEMORYSTATUS` Merry Struktur `GlobalMemoryStatus`.  
  
 Die Common Language Runtime verwendet den Rückgabewert als Heuristik für den Garbage Collector. Wenn der Host meldet, dass die Mehrheit des Arbeitsspeichers verwendet wird, kann z. B. der Garbage Collector entscheiden, Erfassen von mehreren Generierungen, die die Menge an Arbeitsspeicher zu erhöhen, die potenziell verfügbar gemacht werden können.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.GC?displayProperty=nameWithType>  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
