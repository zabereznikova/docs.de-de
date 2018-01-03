---
title: EBindPolicyLevels-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52e4d4522c7401aba198deed7853ccca71752d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels-Enumeration
Enthält Flags, um die Stufe der übernehmen oder Ändern der Assemblyrichtlinie für die anzugeben.  
  
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
|`ePolicyLevelNone`|Gibt keine Richtlinienebene Flags.|  
|`ePolicyLevelPublisher`|Gibt an, dass die Richtlinie auf den Verleger angewendet werden soll.|  
|`ePolicyLevelRetargetable`|Gibt an, dass die Richtlinie auf Variablen Ebenen angewendet werden soll.|  
|`ePolicyPortability`|Gibt an, dass die Richtlinie für Portabilität zwischen Implementierungen von .NET Framework-Assembly unterstützt werden sollen. Finden Sie unter der [ \<SupportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) Element für Konfigurationsdateien.|  
|`ePolicyUnifiedToCLR`|Gibt an, dass die Richtlinie, die common Language Runtime (CLR) vereinheitlicht werden sollte.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration wird an Methoden übergeben der [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) Schnittstelle, um die Änderungen in Anwendungsrichtlinie angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyIdentityManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
