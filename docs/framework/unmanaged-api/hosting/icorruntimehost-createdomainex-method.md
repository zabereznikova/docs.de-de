---
title: ICorRuntimeHost::CreateDomainEx-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a538f14e7dbf24a94343f364201e968bffa757f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158924"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx-Methode
Erstellt eine Anwendungsdomäne. Der Aufrufer empfängt einen Schnittstellenzeiger, der Typ <xref:System._AppDomain>, um eine Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>. Diese Methode ermöglicht den Aufrufer die Übergabe einer IAppDomainSetup-Instanz zum Konfigurieren der zusätzlichen Features des zurückgegebenen <xref:System._AppDomain> Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzFriendlyName`  
 [in] Ein optionaler Parameter verwendet, geben einen benutzerfreundlichen Namen der Domäne. Dieser Anzeigename kann in Benutzeroberflächen wie der Debugger zur Kennzeichnung der Domäne angezeigt werden.  
  
 `pSetup`  
 [in] Ein optionaler Schnittstellenzeiger vom Typ `IAppDomainSetup`, erreicht durch einen Aufruf der [ICorRuntimeHost:: CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) Methode.  
  
 `pIdentityArray`  
 [in] Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die durch Sicherheitsrichtlinien eines Berechtigungssatzes zugeordneten Beweis darstellen. Ein `IIdentity` -Objekt abgerufen werden kann, durch den Aufruf der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) Methode.  
  
 `pAppDomain`  
 [out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um die Domäne noch weiter zu steuern.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vorgang war erfolgreich.|  
|S_FALSE|Der Vorgang konnte nicht abgeschlossen.|  
|E_FAIL|Ein Unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
  
## <a name="remarks"></a>Hinweise  
 `CreateDomainEx` Erweitert die Möglichkeiten von [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) indem ermöglicht den Aufrufer die Übergabe in einem `IAppDomainSetup` Instanz mit Eigenschaftswerten für das Konfigurieren der Anwendungsdomäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Version:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [CreateDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
