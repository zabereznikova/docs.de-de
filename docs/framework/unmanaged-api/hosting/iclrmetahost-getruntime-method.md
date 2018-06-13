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
ms.openlocfilehash: c83f6dfe069b75f1ab3256f4e5a083f85b50adad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435915"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime-Methode
Ruft die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die eine bestimmte Version der common Language Runtime (CLR) entspricht. Diese Methode hat Vorrang vor den [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion, mit der [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Flag.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzVersion`  
 [in] Version von .NET Framework Kompilierung gespeichert, die in den Metadaten, im Format "V*ein*. *B*[. *X*] ". *Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, die Nebenversion und die Nummer des Builds entsprechen.  
  
> [!NOTE]
>  Dieser Parameter muss mit den Namen des Verzeichnisses für die .NET Framework-Version unter C:\Windows\Microsoft.NET\Framework oder C:\Windows\Microsoft.NET\Framework64 übereinstimmen.  
  
 Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *X*", wobei *X* richtet sich nach die Buildnummer installiert. Das Präfix "V" ist erforderlich.  
  
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
 Diese Methode interagiert konsistent mit älteren Schnittstellen wie z. B. die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) Schnittstelle und Legacy-Funktionen wie z. B. die als veraltet markierten `CorBindTo*` Funktionen (finden Sie unter [veraltet CLR Hosting-Funktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in .NET Framework 2.0 hosting-API). D. h. Laufzeiten, die geladen werden, mit dem legacy-API für die neue API sichtbar sind, und Laufzeiten, die mit der neuen API geladen werden, die für die legacy-API sichtbar sind. sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Veraltete CLR-Hostingschnittstellen und Co-Klassen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 [CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
