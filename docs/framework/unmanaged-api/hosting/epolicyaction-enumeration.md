---
title: EPolicyAction-Enumeration
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404cd5513a1cbd353faed41030a80ec2abef235f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774210"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction-Enumeration
Beschreibt die Richtlinienaktionen, der Host kann für Vorgänge, die durch beschrieben festlegen [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) sowie durch beschriebene Fehler [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eAbortThread`|Gibt an, dass die common Language Runtime (CLR) den Thread ordnungsgemäß abgebrochen werden soll. Ein ordnungsgemäßer Abbruch beinhaltet versuchen der Ausführung alle `finally` Blöcke, alle `catch` Blöcke im Zusammenhang mit der Threadabbrüche und Finalizer.|  
|`eDisableRuntime`|Gibt an, dass die CLR deaktiviert eingeben soll. Verwalteter Code kann keine weiteren des betroffenen Prozesses ausgeführt werden, und der CLR Threads blockiert.|  
|`eExitProcess`|Gibt an, dass die CLR dem ordnungsgemäßen Beenden der Prozess, einschließlich der Ausführung von Finalizern und Bereinigung und protokollieren soll.|  
|`eFastExitProcess`|Gibt an, dass die CLR den Prozess sofort beendet werden soll ohne Ausführung von Finalizern oder Bereinigung und Vorgänge. Allerdings wird die Benachrichtigung an den Debugger gesendet.|  
|`eNoAction`|Gibt an, dass keine Aktion ausgeführt werden soll.|  
|`eRudeAbortThread`|Gibt an, dass die CLR einen grobe Threadabbruch ausführen soll. Nur die `catch` und `finally` Blöcke gekennzeichnet mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.|  
|`eRudeExitProcess`|Gibt an, dass die CLR den Prozess beendet werden soll, ohne Ausführung von Finalizern oder Vorgänge protokollieren.|  
|`eRudeUnloadAppDomain`|Gibt an, dass die CLR ein grobe Entladen durchführen, sollten die <xref:System.AppDomain>. Nur Finalizer mit markierten <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden. Auf ähnliche Weise alle Threads mit dieser <xref:System.AppDomain> in ihrem Stapel erhalten eine `ThreadAbortException`, sondern nur die `catch` und `finally` Blöcke gekennzeichnet mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.|  
|`eThrowException`|Gibt an, dass es sich bei der Bedingung, z. B. Out-of-Memory, Pufferüberlauf usw., entsprechende Ausnahme ausgelöst werden soll.|  
|`eUnloadAppDomain`|Gibt an, dass die <xref:System.AppDomain> entladen werden soll. Die CLR versucht, die Finalizer ausgeführt.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host setzt Richtlinienaktionen durch Aufrufen der Methoden der der [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) Schnittstelle. Informationen über grobe und ordnungsgemäße Abbrüche finden Sie unter den [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
