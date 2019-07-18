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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7312a50137ab8a5c066d5e140a1742ee1918b44
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776561"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode
Gibt eine Schnittstelle, die eine Laufzeit darstellt, der ältere Aktivierungsrichtlinie, z. B. mithilfe gebunden wurde, der `useLegacyV2RuntimeActivationPolicy` -Attribut für die [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) Konfigurationsdateieintrag, durch die direkte Verwendung der Legacyaktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Parameter  
 `riid`  
 [in] Der einzige gültige Wert für diesen Parameter ist Required.Currently `IID_ICLRRuntimeInfo`.  
  
 `ppUnk`  
 [out] erforderlich. Bei der Rückgabe dieser Methode enthält einen Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle, die eine Laufzeit darstellt, die an eine ältere Aktivierungsrichtlinie gebunden wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen und hat eine Laufzeit zurückgegeben, die an eine ältere Aktivierungsrichtlinie gebunden wurde.|  
|S_FALSE|Die Methode wurde erfolgreich abgeschlossen, aber eine ältere Laufzeit wurde noch nicht gebunden.|  
|E_NOINTERFACE|Die Methode hat eine Laufzeitumgebung gefunden, die an eine ältere Aktivierungsrichtlinie gebunden war, aber `riid` wird von dieser Laufzeit nicht unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
