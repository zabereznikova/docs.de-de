---
title: IHostMemoryManager::VirtualFree-Methode
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 663c01d7e4b551ecf18bdd85a63aefc43f9750e2
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="ihostmemorymanagervirtualfree-method"></a>IHostMemoryManager::VirtualFree-Methode
Dient als logischer Wrapper für die entsprechenden Win32-Funktion. Die Win32-Implementierung von `VirtualFree` frei, Aufhebung der Zusage, oder freigibt und Aufhebung der Zusage eines von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `lpAddress`  
 [in] Ein Zeiger auf die Basisadresse der Seiten virtueller Arbeitsspeicher freigegeben wird.  
  
 `dwSize`  
 [in] Die Größe in Bytes, des Bereichs, der freigegeben werden.  
  
 `dwFreeType`  
 [in] Der Typ des Vorgangs freigegeben.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`VirtualFree` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_INVALIDOPERATION|Es wurde versucht, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `VirtualFree` zugeordnete Seiten des virtuellen Speichers freigegeben der `lpAddress` Parameter durch einen früheren Aufruf der [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) Funktion. Versuche, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde, sollten HOST_E_INVALIDOPERATION zurückgeben.  
  
 Die Semantik sind identisch mit denen der Win32-Implementierung von `VirtualFree`. Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostMemoryManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [IHostMalloc-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
