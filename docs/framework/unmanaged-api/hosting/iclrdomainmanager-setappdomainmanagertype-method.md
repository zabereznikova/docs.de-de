---
title: ICLRDomainManager::SetAppDomainManagerType-Methode
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c2927195b650f1098292f3d59cd887e084aea21
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490059"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType-Methode
Gibt an, die von abgeleiteten Typ, der <xref:System.AppDomainManager?displayProperty=nameWithType> -Klasse von den Anwendungsdomänen-Manager, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszAppDomainManagerAssembly`  
 [in] Der Anzeigename der Assembly, die die Anwendung-Typ enthält; Zum Beispiel: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 [in] Der Typname, der den Anwendungsdomänen-Manager, einschließlich des Namespaces.  
  
 `dwInitializeDomainFlags`  
 [in] Eine Kombination von [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) Enumerationswerte, der Informationen zu den Anwendungsdomänen-Manager bereitstellen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
  
## <a name="remarks"></a>Hinweise  
 Derzeit die einzige definierte Wert für `dwInitializeDomainFlags` ist `eInitializeNewDomainFlags_NoSecurityChanges`, die der common Language Runtime (CLR) teilt mit, dass die Anwendungsdomänen-Manager nicht während der Ausführung ändern von Sicherheitseinstellungen wird der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode. Dies ermöglicht der CLR, das Laden von Assemblys zu optimieren, die die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA). Dies kann zu einer erheblichen Verbesserung Startzeit führen, wenn der transitive Abschluss von diesem Satz von Assemblys groß ist.  
  
> [!IMPORTANT]
>  Wenn der Host gibt `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungsdomänen-Manager, ein <xref:System.InvalidOperationException> wird ausgelöst, wenn es versucht wird, auf die Sicherheit der Anwendungsdomäne zu ändern.  
  
 Aufrufen der [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)Methode entspricht dem Aufruf `ICLRDomainManager::SetAppDomainManagerType` mit `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags-Enumeration](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
