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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129447"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>EHostBindingPolicyModifyFlags-Enumeration
Ermöglicht dem Host, die Art der Umleitung anzugeben, die Common Language Runtime (CLR) beim Anwenden von Richtlinien Änderungen von einer Quellassembly auf eine Zielassembly ausführen soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Gibt an, dass die CLR Richtlinien Werte der Quellassembly auf die der Zielassembly verkettet.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Gibt an, dass die CLR die Standardaktion ausführt.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Gibt an, dass die CLR die Richtlinien Werte der Zielassembly auf die maximalen Werte festlegt.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Gibt an, dass die CLR Richtlinien Werte der Zielassembly durch die der Quellassembly ersetzen soll.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) -Methode nimmt einen Parameter vom Typ "`EHostBindingPolicyModifyFlags`" an.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRHostBindingPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
