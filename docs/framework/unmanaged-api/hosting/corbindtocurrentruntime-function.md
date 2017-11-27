---
title: CorBindToCurrentRuntime-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: HeaderDef
f1_keywords: CorBindToCurrentRuntime
helpviewer_keywords: CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 630dab4fec8c37bd776b68870a53ab20e4050e06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime-Funktion
Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden. Das Format der XML-Datei ist der standard-Anwendungskonfigurationsdatei nachgebildet. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet. Finden Sie unter [Laden der Common Language Runtime in einen Prozess](http://msdn.microsoft.com/en-us/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwszFileName`  
 [in] Der Name von einer Anwendungskonfigurationsdatei, die angibt, die Version der CLR geladen. Wenn der Dateiname nicht vollständig qualifiziert ist, wird davon ausgegangen werden im gleichen Verzeichnis wie die ausführbare Datei, die den Aufruf.  
  
 Die Version der Laufzeit geladen werden, wird durch das Versionsattribut in beschrieben die [ \<RequiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) Element der Konfigurationsdatei.  
  
 Wenn keine Version angegeben ist, oder wenn die `<requiredRuntime>` Element kann nicht gefunden werden, die neueste Version der CLR, die auf dem Computer installiert ist, wird geladen.  
  
 `rclsid`  
 [in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` der angeforderten Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 [out] Der zurückgegebene Schnittstellenzeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CorBindToRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
