---
title: IHostMemoryManager::VirtualAlloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 761958c44ad374d522a52826929e320e65957ffa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc-Methode
Dient als logischer Wrapper für die entsprechenden Win32-Funktion. Die Win32-Implementierung von `VirtualAlloc` reserviert oder führt einen Commit für einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAddress`  
 [in] Ein Zeiger auf die Startadresse des Bereichs zuweisen.  
  
 `dwSize`  
 [in] Die Größe in Bytes, der Region.  
  
 `flAllocationType`  
 [in] Der Typ der speicherbelegung.  
  
 `flProtect`  
 [in] Arbeitsspeicherschutz für den Bereich der Seiten, die zugeordnet werden soll.  
  
 `dwCriticalLevel`  
 [in] Ein [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Wert, der die Auswirkungen eines zuordnungsfehlers angibt.  
  
 `ppMem`  
 [out] Ein Zeiger auf die Startadresse des belegten Arbeitsspeichers oder Null, wenn die Anforderung nicht erfüllt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die zuordnungsanforderung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Sie reservieren eine Region im Adressraum des Prozesses, durch den Aufruf `VirtualAlloc`. Die `pAddress` Parameter enthält die Startadresse des Speicherblocks werden sollen. Dieser Parameter wird in der Regel festgelegt auf Null. Das Betriebssystem zeichnet freie Adressbereiche für den Prozess verfügbar. Ein `pAddress` Null-Wert weist das System an passenden Bereich zu reservieren. Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen. In beiden Fällen wird die Output-Parameter `ppMem` wird als Zeiger auf den zugeordneten Speicher zurückgegeben. Die Funktion selbst gibt einen HRESULT-Wert zurück.  
  
 Die Win32 `VirtualAlloc` Funktion verfügt nicht über eine `ppMem` Parameter, und gibt stattdessen den Zeiger auf den belegten Speicher zurück. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
