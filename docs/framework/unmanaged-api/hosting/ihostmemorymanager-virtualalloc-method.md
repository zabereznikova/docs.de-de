---
title: IHostMemoryManager::VirtualAlloc-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e5ce46e1cf034e6b86d738d8ec69332df1ff9fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486259"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc-Methode
Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion. Die Win32-Implementierung von `VirtualAlloc` reserviert oder übergibt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pAddress`  
 [in] Ein Zeiger auf die Startadresse des Bereichs zuweisen.  
  
 `dwSize`  
 [in] Die Größe in Bytes des Bereichs.  
  
 `flAllocationType`  
 [in] Der Typ der speicherbelegung.  
  
 `flProtect`  
 [in] Arbeitsspeicherschutz für den Bereich der Seiten, die zugeordnet werden.  
  
 `dwCriticalLevel`  
 [in] Ein [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Wert, der die Auswirkungen eines zuordnungsfehlers angibt.  
  
 `ppMem`  
 [out] Zeiger auf die Startadresse des zugeordneten Speichers oder Null, wenn die Anforderung nicht erfüllt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Anforderung abzuschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Reservieren Sie eine Region in den Adressraum des Prozesses durch den Aufruf `VirtualAlloc`. Die `pAddress` Parameter enthält die Startadresse des Speicherblocks werden sollen. Dieser Parameter wird in der Regel festgelegt auf Null. Das Betriebssystem zeichnet freie Adressbereiche, die für Ihren Prozess zur Verfügung. Ein `pAddress` Null-Wert weist das System an die Region zu reservieren, wo sie Ihr als angemessen erscheint. Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen. In beiden Fällen den Ausgabeparameter `ppMem` wird als Zeiger auf den zugeordneten Speicher zurückgegeben. Die Funktion selbst gibt einen HRESULT-Wert zurück.  
  
 Die Win32 `VirtualAlloc` Funktion verfügt nicht über eine `ppMem` -Parameter und gibt stattdessen den Zeiger auf den reservierten Speicher zurück. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
