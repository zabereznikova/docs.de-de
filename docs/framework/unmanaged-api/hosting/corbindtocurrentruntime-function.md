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
ms.openlocfilehash: 348ca9d157a668dcd180076475f1fe9861197174
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616662"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime-Funktion
Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden. Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../configure-apps/file-schema/index.md).  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert. Weitere Informationen finden Sie [unter Laden der Common Language Runtime in einen Prozess](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
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
  
 Die Version der Laufzeit, die geladen werden soll, wird vom Versions Attribut im Element "Requirements [ \< druntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) " der Konfigurationsdatei beschrieben.  
  
 Wenn keine Version angegeben ist, oder wenn das `<requiredRuntime>` Element nicht gefunden werden kann, wird die aktuelle Version der CLR geladen, die auf dem Computer installiert ist.  
  
 `rclsid`  
 in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` der angeforderten Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 vorgenommen Der zurückgegebene Schnittstellen Zeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorBindToRuntime-Funktion](corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg-Funktion](corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost-Funktion](corbindtoruntimehost-function.md)
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
