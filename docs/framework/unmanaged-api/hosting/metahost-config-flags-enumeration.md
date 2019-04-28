---
title: METAHOST_CONFIG_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e322f5c7119d13c8a872bd87d00c1e55324b581
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765192"
---
# <a name="metahostconfigflags-enumeration"></a>METAHOST_CONFIG_FLAGS-Enumeration
Beschreibt die möglichen Flags, die zurückgegeben werden, der `pdwConfigFlags` Parameter der der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode, gibt das Vorhandensein und die Einstellung des der `useLegacyV2RuntimeActivationPolicy` -Attribut in der [ \<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei.  
  
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
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|Die `useLegacyV2RuntimeActivationPolicy` Attribut wurde nicht im der [ \<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `true`.|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `false`.|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|Übernehmen Sie auf den zurückgegebenen Wert diese Maske `pdwConfigFlags` um die Werte zu erhalten, die relevant für `useLegacyV2RuntimeActivationPolicy`.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Metahost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [\<startup>-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
