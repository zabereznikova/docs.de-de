---
title: IHostMAlloc::Free-Methode
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8bd7b16f06433970d1222dbeaa843e187715faa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438996"
---
# <a name="ihostmallocfree-method"></a>IHostMAlloc::Free-Methode
Speicher, der mit belegt wurde freigegeben wird die [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMem`  
 [in] Ein Zeiger auf den Speicher freigegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Free` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|Es wurde versucht, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `pMem` Parameter verweist auf einen Bereich des Arbeitsspeichers, der nicht belegt wurde, mithilfe eines Aufrufs an `Alloc`, der Host HOST_E_INVALIDOPERATION zurückgeben soll.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
