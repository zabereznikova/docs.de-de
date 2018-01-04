---
title: ICLRRuntimeHost::ExecuteInAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8c540c9618655e6df30ad253e0c4cccdf6624e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>ICLRRuntimeHost::ExecuteInAppDomain-Methode
Gibt an, die <xref:System.AppDomain> in dem den angegebenen verwalteten Code ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `AppDomainId`  
 [in] Die numerische ID des dem <xref:System.AppDomain> in dem die angegebene Methode ausgeführt.  
  
 `pCallback`  
 [in] Ein Zeiger auf die Funktion, die innerhalb des angegebenen ausgeführt <xref:System.AppDomain>.  
  
 `cookie`  
 [in] Ein Zeiger auf nicht transparenten vom Aufrufer reservierten Arbeitsspeicher. Dieser Parameter wird von der common Language Runtime (CLR) an den Domänenrückruf übergeben. Es ist nicht zur Laufzeit verwaltete Heap-Speicher. die Zuordnung und die Lebensdauer dieses Arbeitsspeichers werden vom Aufrufer gesteuert.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `ExecuteInAppDomain`ermöglicht es dem Host, um die Steuerung zu in welchem <xref:System.AppDomain> die angegebene verwaltete Methode ausgeführt werden soll. Sie erhalten eine Anwendungsdomäne-Bezeichner, der auf den Wert der entspricht der <xref:System.AppDomain.Id%2A> Eigenschaft durch den Aufruf [[GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
