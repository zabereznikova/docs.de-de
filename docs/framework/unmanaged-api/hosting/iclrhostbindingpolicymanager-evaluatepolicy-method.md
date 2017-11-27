---
title: ICLRHostBindingPolicyManager::EvaluatePolicy-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.EvaluatePolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7471b77deca7b66ba0a30b08ccf934704a7ac61d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>Parameter  
 `pwzReferenceIdentity`  
 [in] Ein Verweis auf die Assembly vor der richtlinienauswertung.  
  
 `pbApplicationPolicy`  
 [in] Ein Zeiger auf einen Puffer, der enthält die Richtliniendaten.  
  
 `cbAppPolicySize`  
 [in] Die Größe der `pbApplicationPolicy` Puffer.  
  
 `pwzPostPolicyReferenceIdentity`  
 [out] Ein Verweis auf die Assembly nach der Auswertung der neuen Richtliniendaten.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Ein Zeiger auf die Größe des Puffers Assembly Identität Verweis nach der Auswertung der neuen Richtliniendaten.  
  
 `pdwPoliciesApplied`  
 [out] Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) Werte, der angibt, welche Richtlinien angewendet wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Auswertung wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein null-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize`ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `EvaluatePolicy` Methode ermöglicht es dem Host Bindungsrichtlinie hostspezifische Assembly verwalten beeinflusst versionsanforderungen. Das Richtlinienmodul selbst bleibt in der CLR.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
