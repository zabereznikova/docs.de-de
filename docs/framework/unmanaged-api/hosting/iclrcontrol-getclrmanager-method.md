---
title: ICLRControl::GetCLRManager-Methode
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: fa9608423456caeb6020e883a14f2c41583ac4d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126610"
---
# <a name="iclrcontrolgetclrmanager-method"></a>ICLRControl::GetCLRManager-Methode
Ruft einen Schnittstellen Zeiger auf eine Instanz eines der Manager-Typen ab, die der Host zum Konfigurieren des Common Language Runtime (CLR) verwenden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `riid`  
 in Die `IID` des zurück zugebende Manager Typs. Die folgenden `IID` Werte werden unterstützt.  
  
- IID_ICLRDebugManager: gibt an, dass `ppObject` vom Typ [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)sein wird.  
  
- IID_ICLRErrorReportingManager: gibt an, dass `ppObject` vom Typ [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)sein wird.  
  
- IID_ICLRGCManager: gibt an, dass `ppObject` vom Typ [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)sein wird.  
  
- IID_ICLRHostProtectionManager: gibt an, dass `ppObject` vom Typ [iclrhostschutzmanager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)sein wird.  
  
- IID_ICLROnEventManager: gibt an, dass `ppObject` vom Typ [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)sein wird.  
  
- IID_ICLRPolicyManager: gibt an, dass `ppObject` vom Typ [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)sein wird.  
  
- IID_ICLRTaskManager: gibt an, dass `ppObject` vom Typ [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)sein wird.  
  
 `ppObject`  
 vorgenommen Ein Schnittstellen Zeiger auf den angeforderten Manager oder NULL, wenn ein ungültiger Manager-Typ angefordert wurde.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_NOINTERFACE|Der Schnittstellentyp wird nicht unterstützt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
