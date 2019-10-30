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
ms.openlocfilehash: 568c63681b84d0ab3642d84e4a6715ad230582db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120393"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost-Schnittstelle
Bietet ähnliche Funktionen wie die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle, die in der .NET Framework Version 1 bereitgestellt wurde, mit den folgenden Änderungen:  
  
- Das Hinzufügen der [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) -Methode zum Festlegen der Host Steuerelement-Schnittstelle.  
  
- Das Weglassen einiger Methoden, die von `ICorRuntimeHost`bereitgestellt werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ExecuteApplication-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll.|  
|[ExecuteInAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Gibt den <xref:System.AppDomain> an, in dem der angegebene verwaltete Code ausgeführt werden soll.|  
|[ExecuteInDefaultAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly auf.|  
|[GetCLRControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Ruft einen Schnittstellen Zeiger vom Typ [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) ab, den Hosts zum Anpassen der Aspekte des Common Language Runtime (CLR) verwenden können.|  
|[GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Ruft den numerischen Bezeichner des zurzeit ausgeführten <xref:System.AppDomain> ab.|  
|[SetHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Legt die Schnittstelle des Host Steuer Elements fest. Sie müssen `SetHostControl` aufrufen, bevor Sie `Start`aufrufen.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Initialisiert die CLR in einen Prozess.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Beendet die Ausführung des Codes durch die Laufzeit.|  
|[UnloadAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Entlädt die <xref:System.AppDomain>, die dem angegebenen numerischen Bezeichner entspricht.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnen Sie mit der .NET Framework 4, verwenden Sie die [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) -Schnittstelle, um einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle abzurufen, und dann die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode, um einen Zeiger auf `ICLRRuntimeHost`zu erhalten. In früheren Versionen der .NET Framework erhält der Host einen Zeiger auf eine `ICLRRuntimeHost` Instanz durch Aufrufen von [corbindtor untimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Zum Bereitstellen von Implementierungen der Technologien, die in der .NET Framework Version 2,0 bereitgestellt werden, müssen Sie `ICLRRuntimeHost` anstelle von `ICorRuntimeHost`verwenden.  
  
> [!IMPORTANT]
> Rufen Sie die [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) -Methode nicht auf, bevor Sie die [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) -Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren. Wenn die `Start`-Methode zuerst aufgerufen wird, schlägt der `ExecuteApplication` Methodenaufruf fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
