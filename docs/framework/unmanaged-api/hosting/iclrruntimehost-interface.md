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
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965993"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost-Schnittstelle
Bietet ähnliche Funktionen wie die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle, die in der .NET Framework Version 1 bereitgestellt wurde, mit den folgenden Änderungen:  
  
- Das Hinzufügen der [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) -Methode zum Festlegen der Host Steuerelement-Schnittstelle.  
  
- Das Weglassen einiger Methoden, die `ICorRuntimeHost`von bereitgestellt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ExecuteApplication-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll.|  
|[ExecuteInAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Gibt den <xref:System.AppDomain> an, in dem der angegebene verwaltete Code ausgeführt werden soll.|  
|[ExecuteInDefaultAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly auf.|  
|[GetCLRControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ruft einen Schnittstellen Zeiger vom Typ [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) ab, den Hosts zum Anpassen der Aspekte des Common Language Runtime (CLR) verwenden können.|  
|[GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ruft den numerischen Bezeichner der <xref:System.AppDomain> ab, die gerade ausgeführt wird.|  
|[SetHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Legt die Schnittstelle des Host Steuer Elements fest. Sie müssen aufrufen `SetHostControl` , bevor `Start`Sie aufrufen.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Initialisiert die CLR in einen Prozess.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Beendet die Ausführung des Codes durch die Laufzeit.|  
|[UnloadAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Entlädt das <xref:System.AppDomain> , das dem angegebenen numerischen Bezeichner entspricht.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnen Sie mit der .NET Framework 4, indem Sie die [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) -Schnittstelle verwenden, um einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten, und dann die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode aufrufen, um einen Zeiger auf zu `ICLRRuntimeHost`erhalten. In früheren Versionen der .NET Framework erhält der Host einen Zeiger auf eine `ICLRRuntimeHost` Instanz durch Aufrufen von [corbindtor untimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Zum Bereitstellen von Implementierungen der Technologien, die in der .NET Framework Version 2,0 bereitgestellt werden, `ICLRRuntimeHost` müssen Sie `ICorRuntimeHost`anstelle von verwenden.  
  
> [!IMPORTANT]
> Rufen Sie die [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) -Methode nicht auf, bevor Sie die [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) -Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren. Wenn die `Start` -Methode zuerst aufgerufen wird, `ExecuteApplication` kann der Methodenaufruf nicht ausgeführt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
