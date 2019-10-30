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
ms.openlocfilehash: 5c61e2e1208cec0bda1492964a8d02bd71f5a1c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129329"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType-Methode
Gibt den von der <xref:System.AppDomainManager?displayProperty=nameWithType>-Klasse abgeleiteten Typ des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszAppDomainManagerAssembly`  
 in Der Anzeige Name der Assembly, die den Typ des Anwendungs Domänen-Managers enthält. Beispiel: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf 150s00b3".  
  
 `wszAppDomainManagerType`  
 in Der Typname des Anwendungs Domänen-Managers, einschließlich des Namespace.  
  
 `dwInitializeDomainFlags`  
 in Eine Kombination aus [einitializenewdomainflags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) -Enumerationswerten, die Informationen über den Anwendungs Domänen-Manager bereitstellen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
  
## <a name="remarks"></a>Hinweise  
 Derzeit ist der einzige definierte Wert für `dwInitializeDomainFlags` `eInitializeNewDomainFlags_NoSecurityChanges`, der die Common Language Runtime (CLR) anweist, dass der Anwendungs Domänen-Manager während der Ausführung der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>-Methode die Sicherheitseinstellungen nicht ändert. Dadurch kann die CLR das Laden von Assemblys optimieren, die über das APTCA-Attribut (Conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute>) verfügen. Dies kann zu einer erheblichen Verbesserung der Startzeit führen, wenn die transitiv Schließung dieses Assemblysatzes sehr groß ist.  
  
> [!IMPORTANT]
> Wenn der Host `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungs Domänen-Manager angibt, wird eine <xref:System.InvalidOperationException> ausgelöst, wenn versucht wird, die Sicherheit der Anwendungsdomäne zu ändern.  
  
 Das Aufrufen der [ICLRControl:: abtappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)-Methode entspricht dem Aufrufen von `ICLRDomainManager::SetAppDomainManagerType` mit `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags-Enumeration](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
