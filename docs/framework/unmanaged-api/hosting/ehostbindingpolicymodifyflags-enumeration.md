---
title: EHostBindingPolicyModifyFlags-Enumeration
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e8357d20edba993f5a7682f31c04afea4362afd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796057"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags-Enumeration
Ermöglicht dem Host an den Typ der Umleitung, die die common Language Runtime (CLR) durchführen sollten, wenn Änderungen der Richtlinie aus einer Assembly der Ereignisquelle in eine Zielassembly angewendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Gibt an, dass die CLR Richtlinienwerte der Quellassembly auf die der Zielassembly verkettet wird.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Gibt an, dass die CLR die Standardaktion ausgeführt werden.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Gibt an, dass die CLR die Richtlinienwerte der Zielassembly auf die maximalen Werte festgelegt werden.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Gibt an, dass die CLR Richtlinienwerte der Zielassembly mit denen der Quellassembly ersetzt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) Methode nimmt einen Parameter vom Typ `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
