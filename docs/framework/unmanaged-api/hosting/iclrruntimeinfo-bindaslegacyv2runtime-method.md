---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 229c5483c02357054f3d2821d8e024c78887e839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|S_OK|Bindung erfolgreich war oder diese Laufzeit wurde bereits als CLR-Version 2 Aktivierung Richtlinie legacylaufzeit gebunden.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Eine andere Runtime wurde bereits an die ältere 2 Aktivierungsrichtlinie einer CLR-Version gebunden.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die aktuelle Laufzeit bereits für alle legacy CLR Version 2 Aktivierung richtlinienentscheidungen gebunden ist (z. B. mithilfe der `useLegacyV2RuntimeActivationPolicy` -Attribut der [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), diese Methode Ein Fehlerergebnis wird nicht zurückgegeben werden. Stattdessen ist das Ergebnis S_OK zurück, so wie es der Fall wäre, wenn die Methode erfolgreich ältere Aktivierungsrichtlinie gebunden wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [\<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
