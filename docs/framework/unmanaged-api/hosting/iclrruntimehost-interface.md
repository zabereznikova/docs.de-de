---
title: ICLRRuntimeHost-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost
helpviewer_keywords: ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type: apiref
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 247c50eb88f3b1814fd5342ded4ed3c98d4b60a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost-Schnittstelle
Bietet Funktionen, die ähnlich dem Konzept der [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) Schnittstelle bereitgestellt, die in .NET Framework, Version 1, mit den folgenden Änderungen:  
  
-   Das Hinzufügen der [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) Methode zum Festlegen der Schnittstelle des Steuerelements.  
  
-   Die Auslassung einiger Methoden gebotenen `ICorRuntimeHost`.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ExecuteApplication-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|In Szenarien für die ClickOnce-Manifest-basiertes verwendet, an die Anwendung in einer neuen Domäne aktiviert werden.|  
|[ExecuteInAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Gibt an, die <xref:System.AppDomain> in dem den angegebenen verwalteten Code ausgeführt.|  
|[ExecuteInDefaultAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly.|  
|[GetCLRControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ruft einen Schnittstellenzeiger vom Typ [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) Hosts verwenden können, um Aspekte der common Language Runtime (CLR) anzupassen.|  
|[GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ruft den numerischen Bezeichner von die <xref:System.AppDomain> , die gerade ausgeführt.|  
|[SetHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Legt die Host-Schnittstelle. Rufen Sie `SetHostControl` vor dem Aufruf `Start`.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Initialisiert die CLR in einen Prozess an.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Beendet die Ausführung von Code von der Runtime an.|  
|[UnloadAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Entlädt die <xref:System.AppDomain> , die den angegebenen numerischen Bezeichner entspricht.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], verwenden die [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) Schnittstelle, um einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, und rufen Sie anschließend die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) Methode, um einen Zeiger auf `ICLRRuntimeHost`. In früheren Versionen von .NET Framework, der Host Ruft einen Zeiger auf eine `ICLRRuntimeHost` Instanz durch Aufrufen von [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Um Implementierungen der Technologien bereitgestellt, die in .NET Framework, Version 2.0 zu gewährleisten, verwenden Sie `ICLRRuntimeHost` anstelle von `ICorRuntimeHost`.  
  
> [!IMPORTANT]
>  Rufen Sie nicht die [starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) Methode, um ein Manifest-basierten Anwendung aktivieren. Wenn die `Start` -Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CLRRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
