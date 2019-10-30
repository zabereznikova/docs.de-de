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
ms.openlocfilehash: 37919be2d0ebd7d243615bc5845b0781ac13e574
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129316"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>ICLRDomainManager::SetPropertiesForDefaultAppDomain-Methode
Legt Eigenschaften fest, die verwendet werden, um die Standard Anwendungsdomäne zu initialisieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nProperties`  
 in Die Anzahl der Einträge in `pwszPropertyNames` und `pwszPropertyValues`.  
  
 `pwszPropertyNames`  
 in Ein Array von Eigenschaften Namen oder NULL, wenn keine Eigenschaften vorhanden sind. Derzeit ist der einzige Eigenschaftsname, der von dieser Methode erkannt wird, "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 in Ein Array von Eigenschafts Werten oder NULL, wenn keine Eigenschaften vorhanden sind.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` enthält einen Eigenschaftsnamen, der von dieser Methode nicht erkannt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Der Eigenschafts Wert für "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" ist eine Liste von Assemblys mit dem Conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut (APTCA) mit dem <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>-Flag, die für teilweise vertrauenswürdige Aufrufer in der Standard Anwendungsdomäne sichtbar gemacht werden sollen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
