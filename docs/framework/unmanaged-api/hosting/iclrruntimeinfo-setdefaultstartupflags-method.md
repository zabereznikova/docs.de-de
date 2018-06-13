---
title: ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b0871636f816d62c1f65c74d22014d74fb1fb97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433278"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
Legt die Startflags und der Host-Konfigurationsdatei, die zum Starten von der Laufzeitmoduls verwendet wird. Diese Methode ersetzt die Verwendung der `startupFlags` Parameter in der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwStartupFlags`  
 [in] Die Host-Start-Flags festgelegt. Verwenden Sie die gleichen Flags als mit der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.  
  
 `pwzHostConfigFile`  
 [in] Der Verzeichnispfad der Hostkonfigurationsdatei festlegen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Multithread-Host muss Aufrufe dieser Methode synchronisieren. Andernfalls Thread A aufrufen kann die `SetStartupFlags` -Methode nach Abschluss der Thread B einen Aufruf von `SetStartupFlags` und bevor Thread B die Laufzeit gestartet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
