---
title: ICLRErrorReportingManager::BeginCustomDump-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
ms.openlocfilehash: 199c130d70cfbf0d383c2e0dc148ffe3dc1242d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673558"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump-Methode

Gibt die Konfiguration von benutzerdefinierten Heap-Abbilder für die Fehlerberichterstattung an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwFlavor`  
 in Ein [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) -Wert, der die Art des Heap Abbilds angibt, auf dem der benutzerdefinierte Heap Abbild erstellt werden soll.  
  
 `dwNumItems`  
 in Die Länge des `items` Arrays. Wenn `dwFlavor` nicht DUMP_FLAVOR_Mini ist, `dwNumItems` sollte 0 (null) sein.  
  
 `items`  
 in Ein Array von [CustomDumpItem](customdumpitem-structure.md) -Instanzen, das die Elemente angibt, die dem Mini Abbild hinzugefügt werden sollen. Wenn `dwFlavor` nicht DUMP_FLAVOR_Mini ist, `items` sollte NULL sein.  
  
 `dwReserved`  
 [in] Reserviert für zukünftige Verwendung.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `BeginCustomDump` Methode legt die benutzerdefinierte Heap Speicherkonfiguration fest. Die [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) -Methode löscht die benutzerdefinierte Heap Speicherkonfiguration und gibt jeden zugeordneten Zustand frei. Er sollte nach Abschluss des benutzerdefinierten Heap Abbilds aufgerufen werden.  
  
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
