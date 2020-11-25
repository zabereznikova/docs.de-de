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
ms.openlocfilehash: a0992ca8ac4bfffef681c74de455a0eeb627a042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726846"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Gibt an, dass die Richtlinie auf Administratorebene angewendet werden soll.|  
|`ePolicyLevelApp`|Gibt an, dass die Richtlinie auf Anwendungsebene angewendet werden soll.|  
|`ePolicyLevelHost`|Gibt an, dass die Richtlinie auf Hostebene angewendet werden soll.|  
|`ePolicyLevelNone`|Gibt keine Flags auf Richtlinien Ebene an.|  
|`ePolicyLevelPublisher`|Gibt an, dass die Richtlinie auf Verleger Ebene angewendet werden soll.|  
|`ePolicyLevelRetargetable`|Gibt an, dass die Richtlinie auf Variablen Ebenen anwendbar sein soll.|  
|`ePolicyPortability`|Gibt an, dass die Richtlinie die Portabilität zwischen Implementierungen einer .NET Framework Assembly unterstützen soll. Siehe das [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) Element Konfigurationsdatei.|  
|`ePolicyUnifiedToCLR`|Gibt an, dass die Richtlinie für die Common Language Runtime (CLR) vereinheitlicht werden muss.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Enumeration wird an Methoden der [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) -Schnittstelle übermittelt, um Änderungen an der Anwendungs Richtlinie anzugeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRAssemblyIdentityManager-Schnittstelle](iclrassemblyidentitymanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
