---
title: CorBindToRuntimeByCfg-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 3802354bf52cd2aab2a4149d565993b9965e8312
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138299"
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg-Funktion
Lädt die Common Language Runtime (CLR) in einen Prozess, indem Versionsinformationen verwendet werden, die aus einer XML-Datei gelesen werden.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCfgStream`  
 in Ein Zeiger auf ein `IStream` Objekt, das die XML-Datei liest.  
  
 `reserved`  
 in Reserviert für zukünftige Verwendung. 0 (null) als Wert verwenden.  
  
 `startupFlags`  
 in Ein Wert der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumeration, der das Startverhalten der CLR angibt.  
  
 `rclsid`  
 in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) -Schnittstelle implementiert. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 in Die `IID` der `ICorRuntimeHost` oder der `ICLRRuntimeHost`-Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert. Weitere Informationen zu XML-Dateien finden Sie unter [Schema der Konfigurationsdatei](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
