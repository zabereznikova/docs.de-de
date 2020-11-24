---
title: CorBindToCurrentRuntime-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 4a8ab6e1aeedef5b821fc977387b8039f54edd64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682496"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime-Funktion

Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden. Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../configure-apps/file-schema/index.md).  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert. Weitere Informationen finden Sie [unter Laden der Common Language Runtime in einen Prozess](/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pwszFileName`  
 in Der Name einer Anwendungs Konfigurationsdatei, die die Version der zu ladenden CLR angibt. Wenn der Dateiname nicht voll qualifiziert ist, wird davon ausgegangen, dass er sich im gleichen Verzeichnis befindet wie die ausführbare Datei, die den-Vorgang ausführt.  
  
 Die Version der zu ladenden Laufzeit wird durch das Versions Attribut im- [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) Element der Konfigurationsdatei beschrieben.  
  
 Wenn keine Version angegeben ist, oder wenn das `<requiredRuntime>` Element nicht gefunden werden kann, wird die aktuelle Version der CLR geladen, die auf dem Computer installiert ist.  
  
 `rclsid`  
 in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` der angeforderten Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 vorgenommen Der zurückgegebene Schnittstellen Zeiger.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CorBindToRuntime-Funktion](corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg-Funktion](corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost-Funktion](corbindtoruntimehost-function.md)
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
