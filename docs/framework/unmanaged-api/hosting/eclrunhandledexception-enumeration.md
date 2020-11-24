---
title: EClrUnhandledException-Enumeration
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: bccd44e1bead4feadf67929dc104557715904577
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686435"
---
# <a name="eclrunhandledexception-enumeration"></a>EClrUnhandledException-Enumeration

Beschreibt die verfügbaren Optionen zum Verwalten von Ausnahmen, die im Benutzercode nicht behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Gibt an, dass das Standardverhalten auftritt. Der Prozess wird beendet.|  
|`eHostDeterminedPolicy`|Gibt an, dass die Common Language Runtime (CLR) nicht behandelte Ausnahmen ignoriert und der Host jede weitere Aktion bestimmen kann.|  
  
## <a name="remarks"></a>Hinweise  

 Um anzugeben, dass die CLR sich wie frühere Versionen verhält, verwenden Sie den- `eHostDeterminedPolicy` Member.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [EClrOperation-Enumeration](eclroperation-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [SetUnhandledExceptionPolicy-Methode](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [IHostPolicyManager-Schnittstelle](ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
