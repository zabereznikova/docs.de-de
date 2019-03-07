---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da21cda0872080272e6b2c2fda32bef2bf9f1f7d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494531"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode
Ändert die Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzSourceAssemblyIdentity`  
 [in] Die Identität der Assembly, zu ändern.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Die neue Identität der Assembly geändert.  
  
 `pbApplicationPolicy`  
 [in] Ein Zeiger auf einen Puffer, der Daten der Bindung für den zu ändernden Assembly enthält.  
  
 `cbAppPolicySize`  
 [in] Die Größe der Bindungsrichtlinie ersetzt werden.  
  
 `dwPolicyModifyFlags`  
 [in] Eine logische OR-Kombination von [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) Werte, der Kontrolle über die Umleitung angibt.  
  
 `pbNewApplicationPolicy`  
 [out] Ein Zeiger auf einen Puffer, der Daten der neuen Bindung enthält.  
  
 `pcbNewAppPolicySize`  
 [in, out] Ein Zeiger auf die Größe des Puffers Richtlinie neue Bindung.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Richtlinie wurde erfolgreich geändert.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` oder `pwzTargetAssemblyIdentity` wurde ein null-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ModifyApplicationPolicy` -Methode zweimal aufgerufen werden kann. Geben Sie beim erste Aufruf sollte null-Wert für die `pbNewApplicationPolicy` Parameter. Dieser Aufruf gibt den erforderlichen Wert für `pcbNewAppPolicySize`. Der zweite Aufruf sollte diesen Wert für bereitstellen `pcbNewAppPolicySize`, und zeigen Sie auf einen Puffer dieser Größe für `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
