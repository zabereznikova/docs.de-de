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
ms.openlocfilehash: 9840217abdf8b3e1d0917b7447572b6860c181c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720307"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy-Methode

Wertet die Bindungs Richtlinie im Namen des Hosts aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein Verweis auf die Assembly vor der Richtlinien Auswertung.  
  
 `pbApplicationPolicy`  
 in Ein Zeiger auf einen Puffer, der die Richtlinien Daten enthält.  
  
 `cbAppPolicySize`  
 in Die Größe des `pbApplicationPolicy` Puffers.  
  
 `pwzPostPolicyReferenceIdentity`  
 vorgenommen Ein Verweis auf die Assembly nach der Auswertung der neuen Richtlinien Daten.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Ein Zeiger auf die Größe des assemblyidentitätsverweispuffers nach der Auswertung der neuen Richtlinien Daten.  
  
 `pdwPoliciesApplied`  
 vorgenommen Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](ebindpolicylevels-enumeration.md) -Werten, die angibt, welche Richtlinien angewendet wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Auswertung wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein NULL-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `EvaluatePolicy` Methode ermöglicht es dem Host, die Bindungs Richtlinie zu beeinflussen, um Host spezifische assemblyversionsanforderungen beizubehalten. Die Richtlinien-Engine selbst verbleibt innerhalb der CLR.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRHostBindingPolicyManager-Schnittstelle](iclrhostbindingpolicymanager-interface.md)
