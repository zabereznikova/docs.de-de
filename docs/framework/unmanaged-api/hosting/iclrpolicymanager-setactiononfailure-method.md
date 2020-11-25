---
title: ICLRPolicyManager::SetActionOnFailure-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: 8f44247ca7904a40f5ebc092d95c2e08b6048438
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725572"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>ICLRPolicyManager::SetActionOnFailure-Methode

Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `failure`  
 in Einer der [EClrFailure](eclrfailure-enumeration.md) -Werte, der den Typ des Fehlers angibt, für den eine Aktion ausgeführt werden soll.  
  
 `action`  
 in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die durchgeführt werden soll, wenn ein Fehler auftritt. Eine Liste der unterstützten Werte finden Sie im Abschnitt "Hinweise".  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|Eine Richtlinien Aktion kann für den angegebenen Vorgang nicht festgelegt werden, oder für den Vorgang wurde eine ungültige Richtlinien Aktion angegeben.|  
  
## <a name="remarks"></a>Hinweise  

 Standardmäßig löst die CLR eine Ausnahme aus, wenn Sie eine Ressource, z. b. Arbeitsspeicher, nicht zuordnen kann. `SetActionOnFailure` ermöglicht dem Host, dieses Verhalten durch Angeben der Richtlinien Aktion, die bei einem Fehler ausgeführt werden soll, zu überschreiben. In der folgenden Tabelle werden die Kombinationen der unterstützten [EClrFailure](eclrfailure-enumeration.md) -und [EPolicyAction](epolicyaction-enumeration.md) -Werte angezeigt. (Das FAIL_ Präfix wird in [EClrFailure](eclrfailure-enumeration.md) -Werten weggelassen.)  
  
||Nicht criticalresource|Criticalresource|Fatalruntime|Waisen-edlock|StackOverflow|Zugriffsverletzung|Code Contract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||–||  
|ethrowexception|X|X||||–||  
|`eAbortThread`|X|X||||–|X|  
|`eRudeAbortThread`|X|X||||–|X|  
|`eUnloadAppDomain`|X|X||X||–|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|–|X|  
|`eExitProcess`|X|X||X|X|–|X|  
|efastexitprocess|X|X||X|X|–||  
|`eRudeExitProcess`|X|X|X|X|X|–||  
|`eDisableRuntime`|X|X|X|X|X|–||  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
