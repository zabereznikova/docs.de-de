---
title: ICLRRuntimeInfo-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo
helpviewer_keywords: ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type: apiref
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11976e8c147b2c5cab2dd67946b561d703028c8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo-Schnittstelle
Enthält Methoden, die Informationen über eine bestimmte common Language Runtime (CLR), einschließlich der Version, Verzeichnis und Auslastungsstatus zurückgeben. Diese Schnittstelle bietet außerdem laufzeitspezifische Funktionalität ohne Initialisieren der Common Language Runtime. Es enthält die Common Language Runtime-Relative [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) -Methode, die Common Language Runtime-Modul-spezifische [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) -Methode und die Common Language Runtime bereitgestellten Schnittstellen durch die [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)Methode.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Bindet diese Laufzeit für alle legacy CLR Version 2 Aktivierung richtlinienentscheidungen.|  
|[GetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Ruft den CLR-Startflags und Hostkonfigurationsdatei ab.|  
|[GetInterface-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Lädt die CLR in den aktuellen Prozess und gibt Sie Common Language Runtime-Schnittstellenzeiger auf, wie z. B. [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) und [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Diese Methode hat Vorrang vor allen die `CorBindTo*` Funktionen.|  
|[GetProcAddress-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Ruft die Adresse einer angegebenen Funktion, die von der CLR, die diese Schnittstelle zugeordneten exportiert wurde. Diese Methode hat Vorrang vor den [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) Methode.|  
|[GetRuntimeDirectory-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Ruft das Installationsverzeichnis der CLR, die diese Schnittstelle zugeordnet. Diese Methode hat Vorrang vor den [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) Methode.|  
|[GetVersionString-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Ruft die common Language Runtime (CLR)-Versionsinformationen zugeordneten ab einer angegebenen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle. Diese Methode hat Vorrang vor den [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) und [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) Methoden.|  
|[IsLoadable-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Gibt an, ob der aktuelle Prozess ein, und berücksichtigt die Runtime diese Schnittstelle zugeordneten geladen werden kann anderen Laufzeiten, die bereits in den Prozess geladen werden können.|  
|[IsLoaded-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Gibt an, ob die CLR zugeordnet der [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle in einen Prozess geladen wird.|  
|[IsStarted-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Gibt an, ob der CLR zugeordnet ist die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle wurde gestartet.|  
|[LoadErrorString-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur. Diese Methode hat Vorrang vor den [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) und [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) Methoden.|  
|[LoadLibrary-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Lädt eine Bibliothek aus der Frameworkverzeichnis der CLR, dargestellt durch eine [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle. Diese Methode hat Vorrang vor den [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) Methode.|  
|[SetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Die CLR-Startflags und Host festgelegt-Konfigurationsdatei.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
