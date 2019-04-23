---
title: EBindPolicyLevels-Enumeration
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142206"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels-Enumeration
Stellt Flags bereit, die Ebene angegeben, übernehmen oder Ändern von Assemblyrichtlinie an.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Gibt an, dass die Richtlinie auf Administratorebene angewendet werden soll.|  
|`ePolicyLevelApp`|Gibt an, dass die Richtlinie auf Anwendungsebene angewendet werden soll.|  
|`ePolicyLevelHost`|Gibt an, dass die Richtlinie auf der Hostebene angewendet werden soll.|  
|`ePolicyLevelNone`|Gibt keine Flags für die Richtlinie auf Serverebene an.|  
|`ePolicyLevelPublisher`|Gibt an, dass die Richtlinie auf den Verleger angewendet werden soll.|  
|`ePolicyLevelRetargetable`|Gibt an, dass die Richtlinie auf Variablen Ebenen angewendet werden soll.|  
|`ePolicyPortability`|Gibt an, dass die Richtlinie für Portabilität zwischen Implementierungen von .NET Framework-Assembly unterstützen soll. Finden Sie unter den [ \<SupportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) Configuration File-Element.|  
|`ePolicyUnifiedToCLR`|Gibt an, dass die Richtlinie mit der common Language Runtime (CLR) vereinheitlicht werden sollte.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration wird zu Methoden zum Übergeben der [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Schnittstelle, um die Änderungen in der Richtlinie für Anwendungen angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
