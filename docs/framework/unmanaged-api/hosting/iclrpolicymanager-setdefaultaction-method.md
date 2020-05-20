---
title: ICLRPolicyManager::SetDefaultAction-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: c0d8b66c8b85710b0365bfc410188c81431720ff
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703439"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>ICLRPolicyManager::SetDefaultAction-Methode
Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Vorgang auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `operation`  
 in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der die Aktion angibt, für die das CLR-Verhalten angepasst werden soll.  
  
 `action`  
 in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die die CLR bei Auftreten durchführen soll `operation` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_INVALIDARG|`action`Für das wurde ein ungültiges angegeben `operation` , oder für wurde ein ungültiger Wert angegeben `operation` .|  
  
## <a name="remarks"></a>Hinweise  
 Nicht alle Richtlinien Aktionswerte können als Standardverhalten für CLR-Vorgänge angegeben werden. `SetDefaultAction`kann in der Regel nur zum eskalieren des Verhaltens verwendet werden. Beispielsweise kann ein Host angeben, dass Thread Abbrüche in grobe Thread Abbrüche umgewandelt werden, aber nicht das Gegenteil angeben können. In der folgenden Tabelle werden die gültigen `action` Werte für die einzelnen möglichen Werte beschrieben `operation` .  
  
|Wert für`operation`|Gültige Werte für `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|-eabortthread<br />-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_AppDomainRudeUnload|-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_ProcessExit|-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
|OPR_FinalizerRun|-enoaction<br />-eabortthread<br />-erudeabortthread<br />-eUnloadAppDomain<br />-erudeunloadappdomain<br />-eexitprocess<br />-efastexitprocess<br />-eRudeExitProcess<br />-edisableruntime|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrOperation-Enumeration](eclroperation-enumeration.md)
- [EPolicyAction-Enumeration](epolicyaction-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
