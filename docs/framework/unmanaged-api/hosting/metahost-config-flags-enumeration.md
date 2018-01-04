---
title: METAHOST_CONFIG_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_CONFIG_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_CONFIG_FLAGS
helpviewer_keywords: METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5743356cdb2a99c4c5eb0c958bc5ca0815146d4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="metahostconfigflags-enumeration"></a>METAHOST_CONFIG_FLAGS-Enumeration
Beschreibt die möglichen Flags, die zurückgegeben werden, der `pdwConfigFlags` Parameter von der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode, gibt das Vorhandensein und die Einstellung des der `useLegacyV2RuntimeActivationPolicy` Attribut in der [ \<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|Die `useLegacyV2RuntimeActivationPolicy` Attribut war nicht vorhanden, in der [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `true`.|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `false`.|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|Der zurückgegebene Wert in dieser Maske zuweisen `pdwConfigFlags` zum Abrufen der Werte relevant `useLegacyV2RuntimeActivationPolicy`.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Metahost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)  
 [\<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
