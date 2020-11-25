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
ms.openlocfilehash: be006afaf5966aa4e6d11c73b92004d676c97c7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731266"
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
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`VirtualFree` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|Es wurde versucht, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  

 `VirtualFree` gibt `lpAddress` durch einen früheren Aufrufen der [IHostMemoryManager:: virtualbelegc](ihostmemorymanager-virtualalloc-method.md) -Funktion virtuelle Speicherseiten frei, die dem-Parameter zugeordnet sind. Versuche, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde, sollten HOST_E_INVALIDOPERATION zurückgeben.  
  
 Die Semantik ist identisch mit denen der Win32-Implementierung von `VirtualFree` . Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
- [IHostMalloc-Schnittstelle](ihostmalloc-interface.md)
