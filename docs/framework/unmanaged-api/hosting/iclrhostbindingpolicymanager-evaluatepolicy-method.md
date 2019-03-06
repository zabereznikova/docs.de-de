---
title: ICLRHostBindingPolicyManager::EvaluatePolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3310f584475a4d6a6f0e3e790db13875faf60cf2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466686"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy-Methode
Wertet Richtlinien für die Bindung für den Host.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzReferenceIdentity`  
 [in] Ein Verweis auf die Assembly, bevor die richtlinienauswertung.  
  
 `pbApplicationPolicy`  
 [in] Ein Zeiger auf einen Puffer, der die Daten der enthält.  
  
 `cbAppPolicySize`  
 [in] Die Größe der `pbApplicationPolicy` Puffer.  
  
 `pwzPostPolicyReferenceIdentity`  
 [out] Ein Verweis auf die Assembly nach der Auswertung der Daten der neuen.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Ein Zeiger auf die Größe des Puffers Assembly Identität Verweis nach der Auswertung der Daten der neuen.  
  
 `pdwPoliciesApplied`  
 [out] Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) Werte, der angibt, welche Richtlinien angewendet wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Auswertung wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein null-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `EvaluatePolicy` Methode ermöglicht es dem Host Bindungsrichtlinie hostspezifische Assembly verwalten beeinflussen Anforderungen an. Die Richtlinien-Engine selbst bleibt in der CLR.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
