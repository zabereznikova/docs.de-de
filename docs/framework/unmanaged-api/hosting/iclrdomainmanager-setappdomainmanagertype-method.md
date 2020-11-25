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
ms.openlocfilehash: 7c6b328793e6437682ad8d642e611be30e7b0fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702146"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType-Methode

Gibt den von der-Klasse abgeleiteten Typ <xref:System.AppDomainManager?displayProperty=nameWithType> des Anwendungs Domänen-Managers an, der zum Initialisieren der Standard Anwendungsdomäne verwendet wird.  
  
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
 in Eine Kombination aus [einitializenewdomainflags](einitializenewdomainflags-enumeration.md) -Enumerationswerten, die Informationen über den Anwendungs Domänen-Manager bereitstellen.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
  
## <a name="remarks"></a>Hinweise  

 Derzeit ist der einzige definierte Wert für `dwInitializeDomainFlags` `eInitializeNewDomainFlags_NoSecurityChanges` , der die Common Language Runtime (CLR) anweist, dass der Anwendungs Domänen-Manager während der Ausführung der Methode keine Sicherheitseinstellungen ändert <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> . Dadurch kann die CLR das Laden von Assemblys optimieren, die über das Conditional- <xref:System.Security.AllowPartiallyTrustedCallersAttribute> Attribut (APTCA) verfügen. Dies kann zu einer erheblichen Verbesserung der Startzeit führen, wenn die transitiv Schließung dieses Assemblysatzes sehr groß ist.  
  
> [!IMPORTANT]
> Wenn der Host `eInitializeNewDomainFlags_NoSecurityChanges` für den Anwendungs Domänen-Manager angibt, wird eine ausgelöst, <xref:System.InvalidOperationException> Wenn versucht wird, die Sicherheit der Anwendungsdomäne zu ändern.  
  
 Das Aufrufen der [ICLRControl:: abtappdomainmanagertype](iclrcontrol-setappdomainmanagertype-method.md)-Methode entspricht dem Aufrufen `ICLRDomainManager::SetAppDomainManagerType` von mit `eInitializeNewDomainFlags_None` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosting](index.md)
- [ICLRDomainManager-Schnittstelle](iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags-Enumeration](einitializenewdomainflags-enumeration.md)
