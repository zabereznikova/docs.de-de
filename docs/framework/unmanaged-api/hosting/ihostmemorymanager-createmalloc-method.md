---
title: IHostMemoryManager::CreateMAlloc-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 79580170d544cd3763992a4bc67fd20e3446bb1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685720"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a>IHostMemoryManager::CreateMAlloc-Methode

Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Zuordnungs Anforderungen von einem Heap zu erstellen, der vom Host erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwMallocType`  
 in Eine Kombination aus [MALLOC_TYPE](malloc-type-enumeration.md) Flags, die die Merkmale des zugeordneten Speichers angibt.  
  
 `ppMAlloc`  
 vorgenommen Ein Zeiger auf die Adresse einer- `IHostMAlloc` Instanz, die vom Host bereitgestellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`CreateMAlloc` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Zum Abschluss der Zuordnungs Anforderung war nicht genügend physischer Arbeitsspeicher verfügbar.|  
  
## <a name="remarks"></a>Hinweise  

 `CreateMAlloc` Gibt ein-Objekt zurück, das der CLR ermöglicht, Zuordnungs Anforderungen über den Host zu senden, statt die Win32-Standardfunktionen zu verwenden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostMalloc-Schnittstelle](ihostmalloc-interface.md)
- [IHostMemoryManager-Schnittstelle](ihostmemorymanager-interface.md)
