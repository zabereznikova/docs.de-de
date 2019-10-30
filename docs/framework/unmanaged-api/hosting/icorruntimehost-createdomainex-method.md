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
ms.openlocfilehash: a3a2d1827774ddedc00eb849f64256e3f425b3fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127709"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx-Methode
Erstellt eine Anwendungsdomäne. Der Aufrufer erhält einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain>für eine Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>. Diese Methode ermöglicht es dem Aufrufer, eine IAppDomainSetup-Instanz zu übergeben, um zusätzliche Funktionen der zurückgegebenen <xref:System._AppDomain> Instanz zu konfigurieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzFriendlyName`  
 in Ein optionaler Parameter, der verwendet wird, um der Domäne einen anzeigen Amen zu übergeben. Dieser Anzeige Name kann in Benutzeroberflächen wie z. b. Debuggern angezeigt werden, um die Domäne zu identifizieren.  
  
 `pSetup`  
 in Ein optionaler Schnittstellen Zeiger vom Typ `IAppDomainSetup`, der durch einen Aufrufen der [ICorRuntimeHost:: | atedomainsetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) -Methode abgerufen wird.  
  
 `pIdentityArray`  
 in Ein optionales Array von Zeigern auf `IIdentity` Instanzen, die durch Sicherheitsrichtlinien zugeordnete Beweise darstellen, um einen Berechtigungs Satz einzurichten. Ein `IIdentity`-Objekt kann durch Aufrufen der [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) -Methode abgerufen werden.  
  
 `pAppDomain`  
 vorgenommen Ein Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz von <xref:System.AppDomain?displayProperty=nameWithType>, die zur weiteren Steuerung der Domäne verwendet werden kann.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vorgang war erfolgreich.|  
|S_FALSE|Der Vorgang konnte nicht ausgeführt werden.|  
|E_FAIL|Ein unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden. Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
  
## <a name="remarks"></a>Hinweise  
 `CreateDomainEx` erweitert die Funktionen von " [kreatedomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) ", indem es dem Aufrufer ermöglicht, eine `IAppDomainSetup` Instanz mit Eigenschafts Werten zum Konfigurieren der Anwendungsdomäne zu übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Version:** 1,0, 1,1  
  
## <a name="see-also"></a>Siehe auch

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [CreateDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
