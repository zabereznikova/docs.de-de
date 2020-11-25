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
ms.openlocfilehash: 8da9c9fea5cf5b3a27eeb9d0222f0845c832b7da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714197"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode

Ändert die Bindungs Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Die Identität der Assembly, die geändert werden soll.  
  
 `pwzTargetAssemblyIdentity`  
 in Die neue Identität der geänderten Assembly.  
  
 `pbApplicationPolicy`  
 in Ein Zeiger auf einen Puffer, der die Bindungs Richtlinien Daten für die zu ändernde Assembly enthält.  
  
 `cbAppPolicySize`  
 in Die Größe der zu ersetzenden Bindungs Richtlinie.  
  
 `dwPolicyModifyFlags`  
 in Eine logische OR-Kombination von [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) -Werten, die die Steuerung der Umleitung angeben.  
  
 `pbNewApplicationPolicy`  
 vorgenommen Ein Zeiger auf einen Puffer, der die neuen Bindungs Richtlinien Daten enthält.  
  
 `pcbNewAppPolicySize`  
 [in, out] Ein Zeiger auf die Größe des neuen Bindungs Richtlinien Puffers.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Richtlinie wurde erfolgreich geändert.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` oder `pwzTargetAssemblyIdentity` war ein NULL-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `ModifyApplicationPolicy` Methode kann zweimal aufgerufen werden. Der erste-Befehl sollte einen NULL-Wert für den- `pbNewApplicationPolicy` Parameter angeben. Dieser Rückruf gibt mit dem erforderlichen Wert für zurück `pcbNewAppPolicySize` . Der zweite-Befehl sollte diesen Wert für angeben `pcbNewAppPolicySize` und auf einen Puffer dieser Größe für zeigen `pbNewApplicationPolicy` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRHostBindingPolicyManager-Schnittstelle](iclrhostbindingpolicymanager-interface.md)
