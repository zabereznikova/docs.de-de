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
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673773"
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
 [in] Reserviert für zukünftige Verwendung. 0 (null) als Wert verwenden.  
  
 `startupFlags`  
 in Ein Wert der [STARTUP_FLAGS](startup-flags-enumeration.md) -Enumeration, die das Startverhalten der CLR angibt.  
  
 `rclsid`  
 in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 in Der der- `IID` `ICorRuntimeHost` Schnittstelle oder der- `ICLRRuntimeHost` Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen-Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  

 Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert. Weitere Informationen zu XML-Dateien finden Sie unter [Schema der Konfigurationsdatei](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CorBindToCurrentRuntime-Funktion](corbindtocurrentruntime-function.md)
- [CorBindToRuntime-Funktion](corbindtoruntime-function.md)
- [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost-Funktion](corbindtoruntimehost-function.md)
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
