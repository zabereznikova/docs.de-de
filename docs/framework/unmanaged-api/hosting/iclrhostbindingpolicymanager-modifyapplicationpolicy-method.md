---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51775f52e34f35d8ef9f3a8533363be73e9bd7c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode
Ändert eine Bindungsrichtlinie für die für die angegebene Assembly und erstellt eine neue Version der Richtlinie.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `pwzSourceAssemblyIdentity`  
 [in] Die Identität der Assembly zu ändern.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Die neue Identität der geänderten Assembly.  
  
 `pbApplicationPolicy`  
 [in] Ein Zeiger auf einen Puffer, der die Daten der Bindung für die zu ändernde Assembly enthält.  
  
 `cbAppPolicySize`  
 [in] Die Größe der Bindungsrichtlinie ersetzt werden.  
  
 `dwPolicyModifyFlags`  
 [in] Eine logische OR-Kombination von [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) Werte, der Steuerung der Umleitung.  
  
 `pbNewApplicationPolicy`  
 [out] Ein Zeiger auf einen Puffer, der die Daten der neuen Bindung enthält.  
  
 `pcbNewAppPolicySize`  
 [in, out] Ein Zeiger auf die Größe des Puffers Richtlinie neue Bindung.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Richtlinie wurde erfolgreich geändert.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`oder `pwzTargetAssemblyIdentity` wurde ein null-Verweis.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy`ist zu klein.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ModifyApplicationPolicy` Methode zweimal aufgerufen werden kann. Der erste Aufruf sollte Geben Sie einen null-Wert für die `pbNewApplicationPolicy` Parameter. Dieser Aufruf wird zurückgegeben, mit den erforderlichen Wert für `pcbNewAppPolicySize`. Der zweite Aufruf sollte diesen Wert für bereit `pcbNewAppPolicySize`, und zeigen Sie auf einen Puffer der Größe für `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
