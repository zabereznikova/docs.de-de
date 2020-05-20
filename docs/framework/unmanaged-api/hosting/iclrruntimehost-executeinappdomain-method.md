---
title: ICLRRuntimeHost::ExecuteInAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: 505c16cb7ead7950b6d2d6d401730cc3368fb6aa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703293"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>ICLRRuntimeHost::ExecuteInAppDomain-Methode
Gibt den an, <xref:System.AppDomain> in dem der angegebene verwaltete Code ausgeführt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `AppDomainId`  
 in Die numerische ID des <xref:System.AppDomain> , in dem die angegebene Methode ausgeführt werden soll.  
  
 `pCallback`  
 in Ein Zeiger auf die Funktion, die innerhalb des angegebenen ausgeführt werden soll <xref:System.AppDomain> .  
  
 `cookie`  
 in Ein Zeiger auf den nicht transparenten vom Aufrufer zugewiesenen Arbeitsspeicher. Dieser Parameter wird vom Common Language Runtime (CLR) an den Domänen Rückruf übergeben. Es handelt sich nicht um einen von der Laufzeit verwalteten Heap Speicher. die Zuordnung und die Lebensdauer dieses Speichers werden vom Aufrufer gesteuert.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `ExecuteInAppDomain`ermöglicht es dem Host, die Steuerung zu steuern, über welche verwaltete <xref:System.AppDomain> die angegebene verwaltete Methode in ausgeführt werden soll. Sie können den Wert des Bezeichners einer Anwendungsdomäne abrufen, der dem Wert der-Eigenschaft entspricht <xref:System.AppDomain.Id%2A> , indem Sie die [GetCurrentAppDomainId-Methode](iclrruntimehost-getcurrentappdomainid-method.md)aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeHost-Schnittstelle](iclrruntimehost-interface.md)
