---
title: ICLRRuntimeInfo::GetDefaultStartupFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73ad12e99a1ba98f6ea61775155cf1389118f754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags-Methode
Ruft die Startflags und Hostkonfigurationsdatei, die zum Starten von der Laufzeitmoduls verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pdwStartupFlags`  
 [out] Ein Zeiger auf die Host-Start-Flags, die momentan festgelegt sind.  
  
 `pwzHostConfigFile`  
 [out] Ein Zeiger auf den Verzeichnispfad der aktuellen Hostkonfigurationsdatei.  
  
 `pcchHostConfigFile`  
 [in, out] Bei Eingabe, die Größe des `pwzHostConfigFile`, um Pufferüberläufe zu vermeiden. Wenn `pwzHostConfigFile` ist null, gibt die Methode die erforderliche Größe des `pwzHostConfigFile` für Vorabbelegung.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt die Standardwerte für das Flag (`STARTUP_CONCURRENT_GC` und `NULL`), oder von einem vorherigen Aufruf bereitgestellten Werte der [ICLRRuntimeInfo:: SetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), oder legen Sie mit einer der Werte der `CorBind*` Methoden, wenn sie an diese Laufzeit gebunden sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
