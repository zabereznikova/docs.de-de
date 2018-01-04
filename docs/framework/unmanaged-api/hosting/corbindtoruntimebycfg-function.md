---
title: CorBindToRuntimeByCfg-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeByCfg
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeByCfg
helpviewer_keywords: CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dccd777ef20f68d091cfdd7939c57a1f8d42ad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg-Funktion
Lädt die common Language Runtime (CLR) in einen Prozess mithilfe der Versionsinformationen, die aus einer XML-Datei gelesen wird.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCfgStream`  
 [in] Ein Zeiger auf ein `IStream` Objekt, das die XML-Datei liest.  
  
 `reserved`  
 [in] Für zukünftige Verwendung reserviert. Verwenden Sie 0 (null) als Wert ein.  
  
 `startupFlags`  
 [in] Der Wert der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Enumeration, die das Startverhalten der CLR angibt.  
  
 `rclsid`  
 [in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` entweder die `ICorRuntimeHost` oder `ICLRRuntimeHost` Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 [out] Ein Zeiger auf die Adresse für die zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Das Format der XML-Datei ist der standard-Anwendungskonfigurationsdatei nachgebildet. Weitere Informationen zu XML-Dateien, finden Sie unter [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
