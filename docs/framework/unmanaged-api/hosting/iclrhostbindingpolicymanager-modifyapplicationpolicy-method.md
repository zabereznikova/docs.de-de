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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178100"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode
Ändert die Bindungsrichtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.  
  
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
 [in] Die Identität der zu ändernden Assembly.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Die neue Identität der geänderten Assembly.  
  
 `pbApplicationPolicy`  
 [in] Ein Zeiger auf einen Puffer, der die Bindungsrichtliniendaten enthält, die die Assembly ändern soll.  
  
 `cbAppPolicySize`  
 [in] Die Größe der zu ersetzenden Bindungsrichtlinie.  
  
 `dwPolicyModifyFlags`  
 [in] Eine logische ODER-Kombination von [EHostBindingPolicyModifyFlags-Werten,](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) die die Steuerung der Umleitung angibt.  
  
 `pbNewApplicationPolicy`  
 [out] Ein Zeiger auf einen Puffer, der die neuen Bindungsrichtliniendaten enthält.  
  
 `pcbNewAppPolicySize`  
 [in, out] Ein Zeiger auf die Größe des neuen Bindungsrichtlinienpuffers.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Richtlinie wurde erfolgreich geändert.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`oder `pwzTargetAssemblyIdentity` war ein Nullverweis.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE|Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `ModifyApplicationPolicy` Methode kann zweimal aufgerufen werden. Der erste Aufruf sollte einen `pbNewApplicationPolicy` NULL-Wert für den Parameter bereitstellen. Dieser Aufruf wird mit dem `pcbNewAppPolicySize`erforderlichen Wert für zurückgegeben. Der zweite Aufruf sollte `pcbNewAppPolicySize`diesen Wert für bereitstellen und `pbNewApplicationPolicy`auf einen Puffer dieser Größe für verweisen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
