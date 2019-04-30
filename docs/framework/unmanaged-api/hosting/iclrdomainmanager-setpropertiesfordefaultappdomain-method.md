---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c42297e848844617ffdc6c85c81846b5805eb4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984762"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
Legt die Eigenschaften, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nProperties`  
 [in] Die Anzahl der Einträge im `pwszPropertyNames` und `pwszPropertyValues`.  
  
 `pwszPropertyNames`  
 [in] Ein Array von Eigenschaftennamen oder Null, wenn keine Eigenschaften vorhanden sind. Derzeit ist der einzige Eigenschaftenname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 [in] Ein Array von Eigenschaftswerten oder Null, wenn keine Eigenschaften vorhanden sind.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` enthält einen Eigenschaftennamen an, der von dieser Methode nicht erkannt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Der Eigenschaftswert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste der Assemblys, die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA), mit der <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> -Flag, das in der standardanwendung für teilweise vertrauenswürdige Aufrufer sichtbar gemacht werden sollen die Domäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
