---
title: ICLRDomainManager::SetAppDomainManagerType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17c99d21155d8f985ea455e171067855edcafedc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType-Methode
Gibt den Typ abgeleitet wurde. die <xref:System.AppDomainManager?displayProperty=nameWithType> Klasse, der den Anwendungsdomänen-Manager, der verwendet wird, um die Standardanwendungsdomäne zu initialisieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszAppDomainManagerAssembly`  
 [in] Der Anzeigename der Assembly, die den Anwendungstyp der Domänen-Manager enthält; zum Beispiel: "AdMgrExample, Version = 1.0.0.0, Culture = Neutral, PublicKeyToken = 6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 [in] Der Typname des Anwendungsdomänen-Managers, einschließlich des Namespaces.  
  
 `dwInitializeDomainFlags`  
 [in] Eine Kombination von [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) Enumerationswerte, die Informationen zu den Anwendungsdomänen-Manager bereitstellen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Derzeit die einzige definierte Wert für `dwInitializeDomainFlags` ist `eInitializeNewDomainFlags_NoSecurityChanges`, weist der common Language Runtime (CLR), dass die Anwendungsdomänen-Managers nicht während der Ausführung ändern von Sicherheitseinstellungen wird der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode. Dies ermöglicht es der CLR, das Laden von Assemblys zu optimieren, die über die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA). Dies kann zu einer erheblichen Verbesserung Startzeit führen, wenn der transitive Abschluss dieser Gruppe von Assemblys groß ist.  
  
> [!IMPORTANT]
>  Wenn der Host gibt `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungsdomänen-Manager, ein <xref:System.InvalidOperationException> wird ausgelöst, wenn versucht wird, die Sicherheit der Anwendungsdomäne ändern.  
  
 Aufrufen der [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)Methode entspricht dem Aufruf `ICLRDomainManager::SetAppDomainManagerType` mit `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [EInitializeNewDomainFlags-Enumeration](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
