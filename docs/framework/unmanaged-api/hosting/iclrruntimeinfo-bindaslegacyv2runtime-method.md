---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 647c87b6f42b01922a385d502d72410af3140cd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095346"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
Bindet die aktuelle Laufzeit für alle älteren common Language Runtime (CLR) Version 2 Aktivierung richtlinienentscheidungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs zurück:  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Bindung erfolgreich war, oder diese Runtime wurde bereits als CLR-Version 2 Activation-Richtlinie legacylaufzeit gebunden.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Eine andere Runtime wurde bereits an das ältere CLR-Version 2-Aktivierungsrichtlinie gebunden.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die aktuelle Laufzeit bereits für alle älteren CLR-Version 2-Aktivierung richtlinienentscheidungen gebunden ist (z. B. durch Verwendung der `useLegacyV2RuntimeActivationPolicy` -Attribut für die [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), diese Methode Ein Fehlerergebnis wird nicht zurückgegeben wird. Stattdessen ist das Ergebnis S_OK zurück, so wie es der Fall wäre, wenn die Methode erfolgreich ältere Aktivierungsrichtlinie gebunden war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [\<startup>-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
