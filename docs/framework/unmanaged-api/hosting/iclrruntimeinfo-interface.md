---
title: ICLRRuntimeInfo-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo
helpviewer_keywords:
- ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 213fa9fda6b154d4548b4163cc7b5890bfcfb49c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186991"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo-Schnittstelle
Bietet Methoden, die Informationen zu einer bestimmten common Language Runtime (CLR), einschließlich Version, Verzeichnis und Ladestatus zurückgeben. Diese Schnittstelle bietet auch Common Language Runtime-spezifische Funktionen, ohne die persistenzwarteschlange. Es enthält die Common Language Runtime-Relative [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) -Methode, die Laufzeit modulspezifischen [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) -Methode, und die Common Language Runtime bereitgestellten Schnittstellen durch die [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)Methode.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Wird dieser Laufzeit für alle älteren CLR-Version 2 Aktivierung richtlinienentscheidungen gebunden.|  
|[GetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Ruft den CLR-Startflags und Hostkonfigurationsdatei.|  
|[GetInterface-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Lädt die CLR in den aktuellen Prozess und gibt Sie Common Language Runtime-Schnittstellenzeiger auf, wie z. B. [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) und [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Diese Methode ersetzt alle die `CorBindTo*` Funktionen.|  
|[GetProcAddress-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Ruft die Adresse einer angegebenen Funktion, die von der CLR, die dieser Schnittstelle zugeordnet exportiert wurde. Diese Methode ersetzt die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Methode.|  
|[GetRuntimeDirectory-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Ruft ab das Installationsverzeichnis der CLR, die dieser Schnittstelle zugeordnet werden soll. Diese Methode ersetzt die [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) Methode.|  
|[GetVersionString-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Ruft zur common Language Runtime (CLR) Version verknüpft ist, mit einer angegebenen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle. Diese Methode ersetzt die [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) und [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) Methoden.|  
|[IsLoadable-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Gibt an, ob der aktuelle Prozess, die Berücksichtigung die Runtime, die dieser Schnittstelle zugeordnet geladen werden kann anderen Laufzeiten, die bereits in den Prozess geladen werden können.|  
|[IsLoaded-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Gibt an, ob die CLR zugeordnet. die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle in einem Prozess geladen wird.|  
|[IsStarted-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Gibt an, ob der CLR zugeordnet ist die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle wurde gestartet.|  
|[LoadErrorString-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur. Diese Methode ersetzt die [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) und [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) Methoden.|  
|[LoadLibrary-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Lädt eine Bibliothek aus der CLR, dargestellt durch das Framework-Verzeichnis eine [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle. Diese Methode ersetzt die [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) Methode.|  
|[SetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Die CLR-Startflags und Host festgelegt-Konfigurationsdatei.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
