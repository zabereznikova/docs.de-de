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
ms.openlocfilehash: 302db0d029b3811d151473323a7a60bd16a00ec1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131240"
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Gibt an, dass das Standardverhalten auftritt. Der Prozess wird beendet.|  
|`eHostDeterminedPolicy`|Gibt an, dass die Common Language Runtime (CLR) nicht behandelte Ausnahmen ignoriert und der Host jede weitere Aktion bestimmen kann.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `eHostDeterminedPolicy`-Element, um anzugeben, dass die CLR sich wie frühere Versionen verhält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [SetUnhandledExceptionPolicy-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
