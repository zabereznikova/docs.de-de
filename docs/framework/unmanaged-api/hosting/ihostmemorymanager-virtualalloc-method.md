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
ms.openlocfilehash: a2deabc5f1c7ea0f42b6d8ec3944d984854ae571
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731279"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc-Methode

Dient als logischer Wrapper für die entsprechende Win32-Funktion. Die Win32-Implementierung von `VirtualAlloc` reserviert oder übergibt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses.  
  
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
 in Ein [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) -Wert, der die Auswirkung eines Zuordnungs Fehlers angibt.  
  
 `ppMem`  
 vorgenommen Ein Zeiger auf die Startadresse des zugeordneten Speichers oder NULL, wenn die Anforderung nicht erfüllt werden konnte.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Zum Abschluss der Zuordnungs Anforderung war nicht genügend Arbeitsspeicher verfügbar.|  
  
## <a name="remarks"></a>Hinweise  

 Sie reservieren eine Region im Adressraum Ihres Prozesses, indem Sie aufrufen `VirtualAlloc` . Der- `pAddress` Parameter enthält die Anfangsadresse des gewünschten Speicherblocks. Dieser Parameter ist in der Regel auf NULL festgelegt. Das Betriebssystem speichert einen Datensatz mit freien Adressbereichen, die für Ihren Prozess verfügbar sind. `pAddress`Der Wert NULL weist das System an, die Region zu reservieren, wo Sie für Sie geeignet ist. Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen. In beiden Fällen wird der Output-Parameter `ppMem` als Zeiger auf den zugeordneten Speicher zurückgegeben. Die Funktion selbst gibt einen HRESULT-Wert zurück.  
  
 Die Win32 `VirtualAlloc` -Funktion verfügt über keinen `ppMem` -Parameter und gibt stattdessen den Zeiger auf den zugeordneten Arbeitsspeicher zurück. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
