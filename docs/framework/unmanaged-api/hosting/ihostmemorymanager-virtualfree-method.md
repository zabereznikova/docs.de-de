---
title: IHostMemoryManager::VirtualFree-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: b53c0bb38922ae8de048c131807eb32f97423d6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128590"
---
# <a name="ihostmemorymanagervirtualfree-method"></a>IHostMemoryManager::VirtualFree-Methode
Dient als logischer Wrapper für die entsprechende Win32-Funktion. Die Win32-Implementierung von `VirtualFree` Releases, decommitten oder gibt einen Seitenbereich innerhalb des virtuellen Adressraums des aufrufenden Prozesses aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lpAddress`  
 in Ein Zeiger auf die Basisadresse der frei zulegenden virtuellen Speicherseiten.  
  
 `dwSize`  
 in Die Größe des freigegebenen Bereichs in Bytes.  
  
 `dwFreeType`  
 in Der Typ der Freigabe Operation.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualFree` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|Es wurde versucht, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `VirtualFree` gibt mithilfe eines früheren Aufrufes der [IHostMemoryManager:: virtualbelegc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) -Funktion virtuelle Speicherseiten frei, die mit dem `lpAddress` Parameter verknüpft sind. Versuche, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde, sollten HOST_E_INVALIDOPERATION zurückgeben.  
  
 Die Semantik ist identisch mit denen der Win32-Implementierung von `VirtualFree`. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
