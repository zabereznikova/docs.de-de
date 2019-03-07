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
ms.openlocfilehash: 440f2f7c542c697b3d817c988211303c60073979
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492360"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
Legt fest, die Startflags und die Host-Konfigurationsdatei, die verwendet wird, um die Runtime zu starten. Diese Methode ersetzt die Verwendung der `startupFlags` Parameter in der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwStartupFlags`  
 [in] Die Host-Start-Flags festgelegt. Verwenden Sie die gleichen Kennzeichen als mit der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.  
  
 `pwzHostConfigFile`  
 [in] Der Verzeichnispfad der Hostkonfigurationsdatei festlegen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt zurück, die folgende spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Multithread-Host muss Aufrufe dieser Methode synchronisieren. Thread A möglicherweise rufen Sie andernfalls die `SetStartupFlags` Methode auf, nachdem Thread B einen Aufruf von `SetStartupFlags` und Thread B die Laufzeit startet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
