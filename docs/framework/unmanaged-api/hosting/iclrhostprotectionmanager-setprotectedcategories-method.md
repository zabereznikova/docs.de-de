---
title: ICLRHostProtectionManager::SetProtectedCategories-Methode
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141033"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>ICLRHostProtectionManager::SetProtectedCategories-Methode
Gibt an, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `categories`  
 in Eine Kombination aus [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) -Werten, die angibt, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Jeder `EApiCategories` Wert verweist auf eine Liste verwalteter Typen und Member. Die `EApiCategories`-Enumeration und die `SetProtectedCategories`-Methode sind direkt mit der verwalteten <xref:System.Security.Permissions.HostProtectionAttribute>-Klasse verknüpft, mit der verwaltete Typen und Member gekennzeichnet werden, die Funktionen verfügbar machen, die den in `EApiCategories`beschriebenen Kategorien entsprechen. Weitere Informationen finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute> und der <xref:System.Security.Permissions.HostProtectionResource>-Enumeration, die `EApiCategories`direkt entspricht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [EApiCategories-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRHostProtectionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
