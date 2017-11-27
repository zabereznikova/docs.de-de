---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fabf42c16dc41e29ca3d14e00e76797fa8f2a9e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
Legt die Eigenschaften, die verwendet werden, um die Standardanwendungsdomäne zu initialisieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nProperties`  
 [in] Die Anzahl der Einträge im `pwszPropertyNames` und `pwszPropertyValues`.  
  
 `pwszPropertyNames`  
 [in] Ein Array von Namen von Eigenschaften oder Null, wenn keine Eigenschaften vorhanden sind. Derzeit ist der einzige Eigenschaftenname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 [in] Ein Array von Eigenschaftswerten oder Null, wenn keine Eigenschaften vorhanden sind.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames`enthält einen Eigenschaftsnamen, der von dieser Methode nicht erkannt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Der Eigenschaftswert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste der Assemblys, die bedingte <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA) mit dem <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> -Flag, das in der standardanwendung für teilweise vertrauenswürdige Aufrufer sichtbar gemacht werden sollen Domäne.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
