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
ms.openlocfilehash: ec64f9bec0ee9b63796958b17c7f10b87692f1d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686144"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Gibt an, dass die CLR Richtlinien Werte der Quellassembly auf die der Zielassembly verkettet.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Gibt an, dass die CLR die Standardaktion ausführt.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Gibt an, dass die CLR die Richtlinien Werte der Zielassembly auf die maximalen Werte festlegt.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Gibt an, dass die CLR Richtlinien Werte der Zielassembly durch die der Quellassembly ersetzen soll.|  
  
## <a name="remarks"></a>Hinweise  

 Die [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) -Methode nimmt einen Parameter vom Typ an `EHostBindingPolicyModifyFlags` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRHostBindingPolicyManager-Schnittstelle](iclrhostbindingpolicymanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
