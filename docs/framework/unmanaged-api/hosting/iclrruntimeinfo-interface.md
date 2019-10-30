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
ms.openlocfilehash: f6608b03df80fa37ebf5049b53bce46da3e155e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120359"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo-Schnittstelle
Stellt Methoden bereit, die Informationen zu einer bestimmten Common Language Runtime (CLR) zurückgeben, einschließlich Version, Verzeichnis und Ladestatus. Diese Schnittstelle bietet auch Lauf zeitspezifische Funktionen, ohne dass die Laufzeit initialisiert wird. Sie enthält die Lauf Zeit relative [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) -Methode, die Lauf Zeit Modul-spezifische [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) -Methode und die von der Laufzeit bereitgestellte Schnittstellen über die [GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Bindet diese Laufzeit an alle Entscheidungen zur Aktivierung der Common Language Runtime von CLR, Version 2.|  
|[GetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getdefaultstartupflags-method.md)|Ruft die CLR-startflags und die Host Konfigurationsdatei ab.|  
|[GetInterface-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Lädt die CLR in den aktuellen Prozess und gibt Lauf Zeit Schnittstellen Zeiger zurück, z. [b. ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) und [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md). Diese Methode ersetzt alle `CorBindTo*` Funktionen.|  
|[GetProcAddress-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Ruft die Adresse einer angegebenen Funktion ab, die aus der CLR exportiert wurde, die dieser Schnittstelle zugeordnet ist. Diese Methode löst die [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) -Methode aus.|  
|[GetRuntimeDirectory-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Ruft das Installationsverzeichnis der CLR ab, die dieser Schnittstelle zugeordnet ist. Diese Methode löst die [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) -Methode aus.|  
|[GetVersionString-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Ruft die einer bestimmten [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zugeordneten Common Language Runtime (CLR) ab. Diese Methode ersetzt die [getrequestedruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) -Methode und die [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) -Methode.|  
|[IsLoadable-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloadable-method.md)|Gibt an, ob die dieser Schnittstelle zugeordnete Laufzeit in den aktuellen Prozess geladen werden kann, wobei andere Laufzeiten berücksichtigt werden, die möglicherweise bereits in den Prozess geladen wurden.|  
|[IsLoaded-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Gibt an, ob die CLR, die der [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zugeordnet ist, in einen Prozess geladen wird.|  
|[IsStarted-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Gibt an, ob die CLR, die der [iclrruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zugeordnet ist, gestartet wurde.|  
|[LoadErrorString-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur. Diese Methode ersetzt die [LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) -und [LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md) -Methoden.|  
|[LoadLibrary-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Lädt eine Bibliothek aus dem Frameworkverzeichnis der CLR, die durch eine [iclrruntimeingefo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle dargestellt wird. Diese Methode löst die [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) -Methode aus.|  
|[SetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)|Legt die CLR-startflags und die Host Konfigurationsdatei fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
