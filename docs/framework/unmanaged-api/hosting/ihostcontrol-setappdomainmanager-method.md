---
title: IHostControl::SetAppDomainManager-Methode
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: 2f4c004db39c14e7a71b0caa55a6089e8f69ca3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680655"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>IHostControl::SetAppDomainManager-Methode

Benachrichtigt den Host, dass eine Anwendungsdomäne erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwAppDomainID`  
 in Der numerische Bezeichner des ausgewählten <xref:System.AppDomain> .  
  
 `pUnkAppDomainManager`  
 in Ein Zeiger auf das <xref:System.AppDomainManager> Objekt, das der Host als implementiert `IUnknown` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 <xref:System.AppDomainManager>Stellt einen Mechanismus bereit, mit dem ein Bootstrap in verwalteten Code durchgeführt und die Erstellung und die Einstellungen der einzelnen Steuerelemente gesteuert werden können <xref:System.AppDomain> . <xref:System.AppDomainManager>Wird in jedes <xref:System.AppDomain> erstellt, wenn das <xref:System.AppDomain> erstellt wird. Wenn dies der Fall ist, benachrichtigt die CLR den Host, dass die Anwendungsdomäne erstellt wurde, indem der Wert des-Parameters festgelegt wird `pUnkAppDomainManager` .  
  
 In der Implementierung der- `SetAppDomainManager` Methode kann der Host den Assemblynamen und den Typ für den Anwendungs Domänen-Manager festlegen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
