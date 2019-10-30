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
ms.openlocfilehash: d5323538447e083a0c727e43261dd68337182b9b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141078"
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
 in Eine logische OR-Kombination von [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) -Werten, die die Steuerung der Umleitung angeben.  
  
 `pbNewApplicationPolicy`  
 vorgenommen Ein Zeiger auf einen Puffer, der die neuen Bindungs Richtlinien Daten enthält.  
  
 `pcbNewAppPolicySize`  
 [in, out] Ein Zeiger auf die Größe des neuen Bindungs Richtlinien Puffers.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Richtlinie wurde erfolgreich geändert.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` oder `pwzTargetAssemblyIdentity` war ein NULL-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ModifyApplicationPolicy`-Methode kann zweimal aufgerufen werden. Der erste-Befehl sollte einen NULL-Wert für den `pbNewApplicationPolicy`-Parameter angeben. Dieser Rückruf gibt mit dem erforderlichen Wert für `pcbNewAppPolicySize`zurück. Der zweite-Befehl sollte diesen Wert für `pcbNewAppPolicySize`bereitstellen und auf einen Puffer dieser Größe für `pbNewApplicationPolicy`zeigen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
