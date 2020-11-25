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
ms.openlocfilehash: 0557a8f1c7c495950933a44cacd23ada8e84964e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730499"
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
 in Eine Kombination aus [EApiCategories](eapicategories-enumeration.md) -Werten, die angibt, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Jeder `EApiCategories` Wert verweist auf eine Liste verwalteter Typen und Member. Die `EApiCategories` -Enumeration und die- `SetProtectedCategories` Methode sind direkt mit der verwalteten-Klasse verknüpft, mit der verwaltete Typen und Member gekennzeichnet werden, die Funktionen verfügbar machen, <xref:System.Security.Permissions.HostProtectionAttribute> die den in beschriebenen Kategorien entsprechen `EApiCategories` . Weitere Informationen finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute> und in der- <xref:System.Security.Permissions.HostProtectionResource> Enumeration, die direkt entspricht `EApiCategories` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [EApiCategories-Enumeration](eapicategories-enumeration.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICLRHostProtectionManager-Schnittstelle](iclrhostprotectionmanager-interface.md)
