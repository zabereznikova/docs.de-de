---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: 90474a61b16d65565889bd69ef75616804d8bc60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140884"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode
Gibt eine-Schnittstelle zurück, die eine Laufzeit darstellt, an die die Legacy-Aktivierungs Richtlinie gebunden wurde, z. b. mithilfe des `useLegacyV2RuntimeActivationPolicy`-Attributs für den Eintrag [\<Start > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) -Konfigurationsdatei, durch direkte Verwendung der Legacy-Aktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Parameter  
 `riid`  
 in Erforderlich. zurzeit ist der einzige gültige Wert für diesen Parameter `IID_ICLRRuntimeInfo`.  
  
 `ppUnk`  
 [out] erforderlich. Diese Methode gibt einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zurück, die eine Laufzeit darstellt, die an die ältere Aktivierungs Richtlinie gebunden wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen und hat eine Laufzeit zurückgegeben, die an eine ältere Aktivierungsrichtlinie gebunden wurde.|  
|S_FALSE|Die Methode wurde erfolgreich abgeschlossen, aber eine ältere Laufzeit wurde noch nicht gebunden.|  
|E_NOINTERFACE|Die Methode hat eine Laufzeitumgebung gefunden, die an eine ältere Aktivierungsrichtlinie gebunden war, aber `riid` wird von dieser Laufzeit nicht unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
