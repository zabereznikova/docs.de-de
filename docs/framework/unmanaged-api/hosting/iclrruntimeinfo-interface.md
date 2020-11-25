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
ms.openlocfilehash: 9f485728ddb050abf815bf8ba26c69be9c909785
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714971"
---
# <a name="iclrruntimeinfo-interface"></a>ICLRRuntimeInfo-Schnittstelle

Stellt Methoden bereit, die Informationen zu einer bestimmten Common Language Runtime (CLR) zurückgeben, einschließlich Version, Verzeichnis und Ladestatus. Diese Schnittstelle bietet auch Lauf zeitspezifische Funktionen, ohne dass die Laufzeit initialisiert wird. Sie enthält die Lauf Zeit relative [LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) -Methode, die Lauf Zeit Modul-spezifische [GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) -Methode und die von der Laufzeit bereitgestellte Schnittstellen über die [GetInterface](iclrruntimeinfo-getinterface-method.md) -Methode.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[BindAsLegacyV2Runtime-Methode](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Bindet diese Laufzeit an alle Entscheidungen zur Aktivierung der Common Language Runtime von CLR, Version 2.|  
|[GetDefaultStartupFlags-Methode](iclrruntimeinfo-getdefaultstartupflags-method.md)|Ruft die CLR-startflags und die Host Konfigurationsdatei ab.|  
|[GetInterface-Methode](iclrruntimeinfo-getinterface-method.md)|Lädt die CLR in den aktuellen Prozess und gibt Lauf Zeit Schnittstellen Zeiger zurück, z. [b. ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md) und [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md). Diese Methode ersetzt alle `CorBindTo*` Funktionen.|  
|[GetProcAddress-Methode](iclrruntimeinfo-getprocaddress-method.md)|Ruft die Adresse einer angegebenen Funktion ab, die aus der CLR exportiert wurde, die dieser Schnittstelle zugeordnet ist. Diese Methode löst die [GetRealProcAddress](getrealprocaddress-function.md) -Methode aus.|  
|[GetRuntimeDirectory-Methode](iclrruntimeinfo-getruntimedirectory-method.md)|Ruft das Installationsverzeichnis der CLR ab, die dieser Schnittstelle zugeordnet ist. Diese Methode löst die [GetCORSystemDirectory](getcorsystemdirectory-function.md) -Methode aus.|  
|[GetVersionString-Methode](iclrruntimeinfo-getversionstring-method.md)|Ruft die einer bestimmten [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordneten Common Language Runtime (CLR) ab. Diese Methode ersetzt die [getrequestedruntimeingefo](getrequestedruntimeinfo-function.md) -Methode und die [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) -Methode.|  
|[IsLoadable-Methode](iclrruntimeinfo-isloadable-method.md)|Gibt an, ob die dieser Schnittstelle zugeordnete Laufzeit in den aktuellen Prozess geladen werden kann, wobei andere Laufzeiten berücksichtigt werden, die möglicherweise bereits in den Prozess geladen wurden.|  
|[IsLoaded-Methode](iclrruntimeinfo-isloaded-method.md)|Gibt an, ob die CLR, die der [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordnet ist, in einen Prozess geladen wird.|  
|[IsStarted-Methode](iclrruntimeinfo-isstarted-method.md)|Gibt an, ob die CLR, die der [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordnet ist, gestartet wurde.|  
|[LoadErrorString-Methode](iclrruntimeinfo-loaderrorstring-method.md)|Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur. Diese Methode ersetzt die [LoadStringRC](loadstringrc-function.md) -und [LoadStringRCEx](loadstringrcex-function.md) -Methoden.|  
|[LoadLibrary-Methode](iclrruntimeinfo-loadlibrary-method.md)|Lädt eine Bibliothek aus dem Frameworkverzeichnis der CLR, die durch eine [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle dargestellt wird. Diese Methode löst die [LoadLibraryShim](loadlibraryshim-function.md) -Methode aus.|  
|[SetDefaultStartupFlags-Methode](iclrruntimeinfo-setdefaultstartupflags-method.md)|Legt die CLR-startflags und die Host Konfigurationsdatei fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
