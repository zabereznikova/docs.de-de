---
title: ICLRGCManager::SetGCStartupLimits-Methode
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3292fae0ca78615faee4cb5208aa711fea9a0a24
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490007"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>ICLRGCManager::SetGCStartupLimits-Methode
Legt die Größe der eine Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 fest.  
  
> [!IMPORTANT]
>  Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], Sie können die Größe des Segments festlegen und die Größe von maximal Generation 0 zu Werte größer als `DWORD` mithilfe der [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `SegmentSize`  
 [in] Die angegebene Größe der Garbage Collection-Segments.  
  
 Die minimale Segmentgröße ist 4 MB. Segmente können in Inkrementen von 1 MB oder größer sein.  
  
 `MaxGen0Size`  
 [in] Die angegebene maximale Größe für Generation 0.  
  
 Die minimale Generation 0 beträgt 64 KB.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die Werte, die `SetGCStartupLimits` legt können nur einmal angegeben werden. Spätere Aufrufe von `SetGCStartupLimits` werden ignoriert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Automatische Speicherverwaltung](../../../../docs/standard/automatic-memory-management.md)
- [Garbage Collection](../../../../docs/standard/garbage-collection/index.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
