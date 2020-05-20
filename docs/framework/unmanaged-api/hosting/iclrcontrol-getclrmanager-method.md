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
ms.openlocfilehash: 04cb45cd021532b6cb3d74a195cbd62e1ab8d31d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615851"
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
 in Der `IID` des Vorgesetzten Typs, der zurückgegeben werden soll. Die folgenden `IID` Werte werden unterstützt.  
  
- IID_ICLRDebugManager: gibt an, dass den `ppObject` Typ [ICLRDebugManager](iclrdebugmanager-interface.md)aufweisen soll.  
  
- IID_ICLRErrorReportingManager: gibt an, dass den `ppObject` Typ [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)aufweisen soll.  
  
- IID_ICLRGCManager: gibt an, dass den `ppObject` Typ [ICLRGCManager](iclrgcmanager-interface.md)aufweisen soll.  
  
- IID_ICLRHostProtectionManager: gibt an, dass den `ppObject` Typ [iclrhostschutzmanager](iclrhostprotectionmanager-interface.md)aufweisen soll.  
  
- IID_ICLROnEventManager: gibt an, dass den `ppObject` Typ [ICLROnEventManager](iclroneventmanager-interface.md)aufweisen soll.  
  
- IID_ICLRPolicyManager: gibt an, dass den `ppObject` Typ [ICLRPolicyManager](iclrpolicymanager-interface.md)aufweisen soll.  
  
- IID_ICLRTaskManager: gibt an, dass den `ppObject` Typ [ICLRTaskManager](iclrtaskmanager-interface.md)aufweisen soll.  
  
 `ppObject`  
 vorgenommen Ein Schnittstellen Zeiger auf den angeforderten Manager oder NULL, wenn ein ungültiger Manager-Typ angefordert wurde.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|E_NOINTERFACE|Der Schnittstellentyp wird nicht unterstützt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [IHostControl-Schnittstelle](ihostcontrol-interface.md)
