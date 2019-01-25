---
title: ICLRMetaHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b52b12df9953dbafaeebfe223313288de0e559b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584047"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost-Schnittstelle
Enthält Methoden, die eine bestimmte Version der common Language Runtime (CLR) basierend auf ihrer Versionsnummer zurückgeben, alle installierten clrs, Listen Sie alle Laufzeiten, die in einem angegebenen Prozess geladen werden, ermitteln die CLR-Version, die zum Kompilieren einer Assembly, einen Prozess beenden mit einer sauberen Runtime beendet, und die legacy-API abfragebindung.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Gibt eine Enumeration, die eine gültige enthält [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellenzeiger für jede CLR-Version, die auf einem Computer installiert ist.|  
|[EnumerateLoadedRuntimes-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Gibt eine Enumeration, die eine gültige enthält [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellenzeiger für jede CLR, die in einem bestimmten Prozess geladen wird. Diese Methode ersetzt [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).|  
|[ExitProcess-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren und beendet dann den Prozess. Hat Vorrang vor den [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) Funktion.|  
|[GetRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Ruft die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die einer bestimmten CLR-Version entspricht. Diese Methode ersetzt die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) , die mit verwendet die [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Flag.|  
|[GetVersionFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Ruft der Assembly .NET Framework Kompilierung Originalversion (gespeichert in den Metadaten), wenn ihr Dateipfad ab. Diese Methode ersetzt [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).|  
|[QueryLegacyV2RuntimeBinding-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Gibt eine Schnittstelle, die eine Laufzeit darstellt, der ältere Aktivierungsrichtlinie, z. B. mithilfe gebunden wurde, der `useLegacyV2RuntimeActivationPolicy` -Attribut für die [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) Konfigurationsdateieintrag, durch die direkte Verwendung der Legacyaktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) Methode.|  
|[RequestRuntimeLoadedNotification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Einen Rückruf an den angegebenen Funktionszeiger garantiert, wenn eine CLR-Version zum ersten Mal geladen, aber noch nicht gestartet. Diese Methode ersetzt [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>Hinweise  
 Die einzige Möglichkeit, eine Instanz dieser Schnittstelle wird durch Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) -Funktion wie folgt:  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
