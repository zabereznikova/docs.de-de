---
title: ICLRMetaHost::GetRuntime-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b71d0f29d770b2722b0dfaabc8b9667e524c99e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984606"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime-Methode
Ruft die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die eine bestimmte Version der common Language Runtime (CLR) entspricht. Diese Methode ersetzt die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) , die mit verwendet die [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Flag.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzVersion`  
 [in] In den Metadaten, in dem Format gespeichert .NET Framework-Kompilierung, Version "V*ein*. *B*[. *X*] ". *Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, Nebenversion und die Nummer des Builds entsprechen.  
  
> [!NOTE]
>  Dieser Parameter muss den Verzeichnisnamen für die .NET Framework-Version übereinstimmen, wie er unter C:\Windows\Microsoft.NET\Framework oder C:\Windows\Microsoft.NET\Framework64 angezeigt wird.  
  
 Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *X*", wobei *X* hängt von der Nummer des Builds installiert. Das Präfix "V" ist erforderlich.  
  
 `riid`  
 [in] Der Bezeichner für die gewünschte Schnittstelle. Derzeit ist der einzige gültige Wert für diesen Parameter "IID_ICLRRuntimeInfo".  
  
 `ppRuntime`  
 [out] Ein Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die der angeforderten Laufzeit entspricht.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pwzVersion` oder `ppRuntime` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode interagiert konsistent mit legacy-Schnittstellen wie z. B. die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -Schnittstelle und Legacy-Funktionen wie z. B. die veraltete `CorBindTo*` Funktionen (finden Sie unter [veraltet CLR Hosting-Funktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in .NET Framework 2.0 hosting-API). Also mit der legacy-API geladenen Laufzeiten für die neue API sichtbar sind, und mit der neuen API geladenen Laufzeiten für die legacy-API sichtbar sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
