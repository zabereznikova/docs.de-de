---
title: ICLRErrorReportingManager::EndCustomDump-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
ms.openlocfilehash: feaeba15fcc4e8264f7fde57d3b268a6b583ad83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677829"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a>ICLRErrorReportingManager::EndCustomDump-Methode

Entfernt die benutzerdefinierte Stapel Sicherungs Konfiguration, die in einem früheren Aufrufen der [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) -Methode angegeben wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`EndCustomDump` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapel Sicherungs Konfiguration, die durch einen früheren Aufrufe der-Methode festgelegt wurde, `BeginCustomDump` und gibt jeden zugeordneten Zustand frei Er sollte nach Abschluss des benutzerdefinierten Stapel Abbilds aufgerufen werden.  
  
> [!IMPORTANT]
> Wenn Sie den Vorgang nicht aufzurufen, ist der `EndCustomDump` Speicherfehler  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CustomDumpItem-Struktur](customdumpitem-structure.md)
- [ECustomDumpFlavor-Enumeration](ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager-Schnittstelle](iclrerrorreportingmanager-interface.md)
