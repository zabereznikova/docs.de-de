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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178084"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>ICLRGCManager::SetGCStartupLimits-Methode
Legt die Größe eines Garbage Collection-Segments und die maximale Größe der Generation 0 des Garbage Collection-Systems fest.  
  
> [!IMPORTANT]
> Ab .NET Framework 4.5 können Sie die Segmentgröße und die `DWORD` maximale Größe der Generation 0 auf Werte festlegen, die größer sind als die [ICLRGCManager2::SetGCStartupLimitsEx-Methode.](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `SegmentSize`  
 [in] Die angegebene Größe eines Garbage Collection-Segments.  
  
 Die minimale Segmentgröße beträgt 4 MB. Segmente können in Schritten von 1 MB oder größer vergrößert werden.  
  
 `MaxGen0Size`  
 [in] Die angegebene maximale Größe für Generation 0.  
  
 Die Minimale Größe der Generation 0 beträgt 64 KB.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits`erfolgreich zurückgegeben werden.|  
|HOST_E_CLRNOTAVAILABLE|Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout für den Anruf.|  
|HOST_E_NOT_OWNER|Der Aufrufer besitzt die Sperre nicht.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.|  
|E_FAIL|Ein unbekannter katastrophaler Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Werte, die festgelegt werden, `SetGCStartupLimits` können nur einmal angegeben werden. Spätere `SetGCStartupLimits` Aufrufe werden ignoriert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [Automatische Speicherbereinigung](../../../standard/garbage-collection/index.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
