---
title: ICorRuntimeHost::CloseEnum-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 961fd6693d3a70f28fdfba8635452d4f4d943fc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437195"
---
# <a name="icorruntimehostcloseenum-method"></a>ICorRuntimeHost::CloseEnum-Methode
Setzt einen Domänenenumerator wieder an den Anfang der Domänenliste aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hEnum`  
 [in] Der Enumerator zurückgesetzt.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Vorgang war erfolgreich.|  
|S_FALSE|Der Vorgang konnte nicht abgeschlossen werden.|  
|E_FAIL|Ein Unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann. Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch  
 [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
