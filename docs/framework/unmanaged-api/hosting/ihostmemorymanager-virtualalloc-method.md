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
ms.openlocfilehash: dd588fa85ff8aaa396a8d0e52a738ada46c2a9b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128618"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc-Methode
Dient als logischer Wrapper für die entsprechende Win32-Funktion. Die Win32-Implementierung von `VirtualAlloc` reserviert oder führt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein Zeiger auf die Startadresse des zuzuordnenden Bereichs.  
  
 `dwSize`  
 in Die Größe (in Bytes) der Region.  
  
 `flAllocationType`  
 in Der Typ der Speicher Belegung.  
  
 `flProtect`  
 in Arbeitsspeicher Schutz für den Bereich von Seiten, die zugeordnet werden sollen.  
  
 `dwCriticalLevel`  
 in Ein [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) -Wert, der die Auswirkung eines Zuordnungs Fehlers angibt.  
  
 `ppMem`  
 vorgenommen Ein Zeiger auf die Startadresse des zugeordneten Speichers oder NULL, wenn die Anforderung nicht erfüllt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Zum Abschluss der Zuordnungs Anforderung war nicht genügend Arbeitsspeicher verfügbar.|  
  
## <a name="remarks"></a>Hinweise  
 Sie reservieren eine Region im Adressraum Ihres Prozesses, indem Sie `VirtualAlloc`aufrufen. Der `pAddress`-Parameter enthält die Anfangsadresse des gewünschten Speicherblocks. Dieser Parameter ist in der Regel auf NULL festgelegt. Das Betriebssystem speichert einen Datensatz mit freien Adressbereichen, die für Ihren Prozess verfügbar sind. Ein `pAddress` Wert von NULL weist das System an, die Region zu reservieren, wo Sie passt. Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen. In beiden Fällen wird der Output-Parameter `ppMem` als Zeiger auf den zugeordneten Speicher zurückgegeben. Die Funktion selbst gibt einen HRESULT-Wert zurück.  
  
 Die Win32-`VirtualAlloc` Funktion verfügt über keinen `ppMem`-Parameter und gibt stattdessen den Zeiger auf den zugeordneten Arbeitsspeicher zurück. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
