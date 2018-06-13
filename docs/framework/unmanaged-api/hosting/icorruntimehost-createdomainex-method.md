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
ms.openlocfilehash: 2e851cf16e4b23b1f8510c4d96b23c01eb726a77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438053"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx-Methode
Erstellt eine Anwendungsdomäne. Der Aufrufer empfängt einen Schnittstellenzeiger, der Typ <xref:System._AppDomain>, um eine Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>. Diese Methode ermöglicht den Aufrufer die Übergabe einer IAppDomainSetup-Instanz so konfigurieren zusätzliche Funktionen des zurückgegebenen <xref:System._AppDomain> Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzFriendlyName`  
 [in] Ein optionaler Parameter verwendet, um der Domäne einen Anzeigenamen zuweisen. Dieser aussagekräftige Name kann in Benutzeroberflächen wie Debuggern zur Kennzeichnung der Domäne angezeigt werden.  
  
 `pSetup`  
 [in] Ein optionaler Schnittstellenzeiger vom Typ `IAppDomainSetup`, erhalten Sie durch einen Aufruf der [ICorRuntimeHost:: CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) Methode.  
  
 `pIdentityArray`  
 [in] Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die Beweise Sicherheitsrichtlinie darstellen herstellen einen Berechtigungssatz zugeordnet. Ein `IIdentity` -Objekt abgerufen werden kann, durch Aufrufen der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) Methode.  
  
 `pAppDomain`  
 [out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz von <xref:System.AppDomain?displayProperty=nameWithType> , die verwendet werden kann, um der Domäne weiter zu steuern.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vorgang war erfolgreich.|  
|S_FALSE|Der Vorgang konnte nicht abgeschlossen werden.|  
|E_FAIL|Ein Unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann. Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
  
## <a name="remarks"></a>Hinweise  
 `CreateDomainEx` Erweitert die Fähigkeiten von [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) indem ermöglicht den Aufrufer die Übergabe in einem `IAppDomainSetup` Instanz mit Eigenschaftswerten für das Konfigurieren der Anwendungsdomäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Version:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [CreateDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
