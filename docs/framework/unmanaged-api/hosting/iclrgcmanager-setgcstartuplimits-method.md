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
ms.openlocfilehash: 169d344975762b97f89e8dc32d72f2b9c95fea11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678167"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>ICLRGCManager::SetGCStartupLimits-Methode

Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.  
  
> [!IMPORTANT]
> Beginnend mit dem .NET Framework 4,5 können Sie die Segmentgröße und die maximale Generation 0-Größe auf Werte festlegen, die größer als sind, `DWORD` indem Sie die [ICLRGCManager2:: setgcstartuplimitsex](iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `SegmentSize`  
 in Die angegebene Größe eines Garbage Collection Segments.  
  
 Die minimale Segmentgröße beträgt 4 MB. Segmente können in Inkrementen von mindestens 1 MB erhöht werden.  
  
 `MaxGen0Size`  
 in Die angegebene maximale Größe für die Generation 0.  
  
 Die Mindestgröße der Generation 0 beträgt 64 KB.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Die Werte, die von `SetGCStartupLimits` festgelegt werden, können nur einmal angegeben werden. Spätere Aufrufe von `SetGCStartupLimits` werden ignoriert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICLRGCManager-Schnittstelle](iclrgcmanager-interface.md)
