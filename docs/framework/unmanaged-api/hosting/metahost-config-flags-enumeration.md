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
ms.openlocfilehash: 01e55659bf2a348ec763f51112cbdcd706f27c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730005"
---
# <a name="metahost_config_flags-enumeration"></a>METAHOST_CONFIG_FLAGS-Enumeration

Beschreibt die möglichen Flags, die im- `pdwConfigFlags` Parameter der [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode zurückgegeben werden, und gibt das vorhanden sein und das Festlegen des- `useLegacyV2RuntimeActivationPolicy` Attributs im- [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|Das- `useLegacyV2RuntimeActivationPolicy` Attribut war nicht im- [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md)vorhanden.|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|Das `useLegacyV2RuntimeActivationPolicy` -Attribut war vorhanden und auf festgelegt `true` .|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|Das `useLegacyV2RuntimeActivationPolicy` -Attribut war vorhanden und auf festgelegt `false` .|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|Wenden Sie diese Maske auf den in zurückgegebenen Wert `pdwConfigFlags` an, um die für relevanten Werte zu erhalten `useLegacyV2RuntimeActivationPolicy` .|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](hosting-enumerations.md)
- [GetRequestedRuntime-Methode](iclrmetahostpolicy-getrequestedruntime-method.md)
- [\<startup>-Element](../../configure-apps/file-schema/startup/startup-element.md)
