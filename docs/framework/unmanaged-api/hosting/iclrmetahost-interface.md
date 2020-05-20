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
ms.openlocfilehash: 391adc6f9fe55ad7ca527ea416956ab013a27b15
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703724"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost-Schnittstelle
Stellt Methoden bereit, die eine bestimmte Version des Common Language Runtime (CLR) basierend auf Ihrer Versionsnummer zurückgeben, alle installierten clrs auflisten, alle Laufzeiten auflisten, die in einem angegebenen Prozess geladen wurden, die CLR-Version ermitteln, die zum Kompilieren einer Assembly verwendet wird, einen Prozess mit einem fehlerhaften Herunterfahren der Laufzeit beenden und eine Abfrage der Legacy-API-Bindung ausführen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede CLR-Version enthält, die auf einem Computer installiert ist.|  
|[EnumerateLoadedRuntimes-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede CLR enthält, die in einem bestimmten Prozess geladen wird. Diese Methode löst " [GetVersionFromProcess](getversionfromprocess-function.md)" aus.|  
|[ExitProcess-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Versucht, alle geladenen Laufzeiten ordnungsgemäß herunterzufahren, und beendet dann den Vorgang. Ersetzt die [CorExitProcess](corexitprocess-function.md) -Funktion.|  
|[GetRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Ruft die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle ab, die einer bestimmten CLR-Version entspricht. Diese Methode ersetzt die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) -Funktion, die mit dem [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) -Flag verwendet wird.|  
|[GetVersionFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Ruft die ursprüngliche .NET Framework Kompilierungs Version der Assembly (gespeichert in den Metadaten) ab, wenn Ihr Dateipfad angegeben ist. Diese Methode ersetzt [GetFileVersion](getfileversion-function.md).|  
|[QueryLegacyV2RuntimeBinding-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Gibt eine-Schnittstelle zurück, die eine Laufzeit darstellt, an die die Legacy-Aktivierungs Richtlinie gebunden wurde, z. b. durch die Verwendung des- `useLegacyV2RuntimeActivationPolicy` Attributs für den Eintrag der [ \< Start> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) -Konfigurationsdatei, durch direkte Verwendung der Legacy-Aktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) -Methode.|  
|[RequestRuntimeLoadedNotification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Garantiert einen Rückruf für den angegebenen Funktionszeiger, wenn eine CLR-Version zum ersten Mal geladen, aber noch nicht gestartet wurde. Diese Methode ersetzt [LockClrVersion](lockclrversion-function.md) .|  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine Instanz dieser Schnittstelle nur abrufen, indem Sie die [CLRCreateInstance](clrcreateinstance-function.md) -Funktion wie folgt aufrufen:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hostingschnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
