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
ms.openlocfilehash: 81aef6beb9ee6d622519738d24fdd0a4d42a75b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136552"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels-Enumeration
Stellt Flags bereit, um die Ebene anzugeben, auf der die Assemblyrichtlinie angewendet oder geändert werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`ePolicyLevelHost`|Gibt an, dass die Richtlinie auf Hostebene angewendet werden soll.|  
|`ePolicyLevelNone`|Gibt keine Flags auf Richtlinien Ebene an.|  
|`ePolicyLevelPublisher`|Gibt an, dass die Richtlinie auf Verleger Ebene angewendet werden soll.|  
|`ePolicyLevelRetargetable`|Gibt an, dass die Richtlinie auf Variablen Ebenen anwendbar sein soll.|  
|`ePolicyPortability`|Gibt an, dass die Richtlinie die Portabilität zwischen Implementierungen einer .NET Framework Assembly unterstützen soll. Weitere Informationen finden Sie unter [\<supportportabili>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) Configuration File-Element.|  
|`ePolicyUnifiedToCLR`|Gibt an, dass die Richtlinie für die Common Language Runtime (CLR) vereinheitlicht werden muss.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration wird an Methoden der [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) -Schnittstelle übermittelt, um Änderungen an der Anwendungs Richtlinie anzugeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
