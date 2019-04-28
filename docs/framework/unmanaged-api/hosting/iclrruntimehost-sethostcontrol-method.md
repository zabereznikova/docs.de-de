---
title: ICLRRuntimeHost::SetHostControl-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6817a2154e876dfa83540e3496f42acdcdb25a83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771812"
---
# <a name="iclrruntimehostsethostcontrol-method"></a>ICLRRuntimeHost::SetHostControl-Methode
Legt den Schnittstellenzeiger auf, die die common Language Runtime (CLR) verwenden können, um die die Implementierung der Hosts erhalten [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pHostControl`  
 [in] Einen Schnittstellenzeiger auf das die Implementierung der Hosts [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`SetHostControl` wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_CLR_ALREADY_STARTED|Die CLR wurde bereits initialisiert.|  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie `SetHostControl` bevor die CLR, d. h. initialisiert wird vor dem Aufruf [Methode starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) oder eines der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md). Es wird empfohlen, die Sie aufrufen `SetHostControl` sofort nach dem Aufruf [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) oder [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
