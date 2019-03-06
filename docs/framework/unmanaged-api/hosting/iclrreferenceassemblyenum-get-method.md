---
title: ICLRReferenceAssemblyEnum::Get-Methode
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63351d15cfe5f085940306e204ee5f6200ee8494
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469169"
---
# <a name="iclrreferenceassemblyenumget-method"></a>ICLRReferenceAssemblyEnum::Get-Methode
Ruft die Identität der Assembly am angegebenen Index ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwIndex`  
 [in] Der nullbasierte Index, der die Identität der Assembly zurückgegeben werden soll.  
  
 `pwzBuffer`  
 [out] Ein Puffer mit der Assemblyidentitätsdaten.  
  
 `pcchBufferSize`  
 [in, out] Die Größe der `pwzBuffer` Puffer.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`Get` wurde erfolgreich zurückgegeben.|  
|ERROR_INSUFFICIENT_BUFFER|`pwzBuffer` ist zu klein.|  
|ERROR_NO_MORE_ITEMS|Die Enumeration enthält keine Elemente mehr.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `Get` wird in der Regel zweimal aufgerufen werden. Der erste Aufruf stellt einen null-Wert für `pwzBuffer`, und legt `pcchBufferSize` auf die Größe, die für die entsprechenden `pwzBuffer`. Beim zweiten Aufruf wird ein geeigneter Größe `pwzBuffer`, und enthält Identitätsdaten kanonische Assembly Fertigstellung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
