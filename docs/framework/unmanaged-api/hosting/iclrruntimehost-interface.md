---
title: ICLRRuntimeHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed32fe643a7722eaf1af38e6079096194690e950
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771890"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost-Schnittstelle
Stellt die Funktionalität ähnelt der von der [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) Schnittstelle, die in .NET Framework, Version 1, mit den folgenden Änderungen:  
  
- Das Hinzufügen der [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) Methode zum Festlegen der Schnittstelle des Steuerelements.  
  
- Die Auslassung einiger Methoden, die von bereitgestellte `ICorRuntimeHost`.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ExecuteApplication-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|In Szenarien für die ClickOnce-Manifest-basierten verwendet, an die Anwendung in einer neuen Domäne aktiviert werden.|  
|[ExecuteInAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Gibt an, die <xref:System.AppDomain> in dem den angegebenen verwalteten Code ausgeführt.|  
|[ExecuteInDefaultAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly.|  
|[GetCLRControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ruft einen Schnittstellenzeiger vom Typ [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) Hosts verwenden können, um Aspekte der common Language Runtime (CLR) anpassen.|  
|[GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ruft den numerischen Bezeichner des der <xref:System.AppDomain> , die derzeit ausgeführt wird.|  
|[SetHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Legt die Schnittstelle des Steuerelements fest. Rufen Sie `SetHostControl` vor dem Aufruf `Start`.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Initialisiert die CLR in einen Prozess an.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Beendet die Ausführung von Code von der Laufzeit.|  
|[UnloadAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Entlädt die <xref:System.AppDomain> , die dem angegebenen numerischen Bezeichner entspricht.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], verwenden die [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) -Schnittstelle zum Abrufen der eines Zeigers auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, und rufen dann die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode zum Abrufen der eines Zeigers auf `ICLRRuntimeHost`. In früheren Versionen von .NET Framework, ruft der Host einen Zeiger auf ein `ICLRRuntimeHost` Instanz durch den Aufruf [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Um die Technologien, die in .NET Framework, Version 2.0 bereitgestellten Implementierungen bereitzustellen, müssen Sie verwenden `ICLRRuntimeHost` anstelle von `ICorRuntimeHost`.  
  
> [!IMPORTANT]
>  Rufen Sie nicht die [starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) Methode, um eine manifestbasierte Anwendung zu aktivieren. Wenn die `Start` Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
