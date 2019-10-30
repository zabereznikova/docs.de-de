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
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138230"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction-Enumeration
Beschreibt die Richtlinien Aktionen, die der Host für Vorgänge festlegen kann, die durch [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) und Fehler beschrieben werden, die von [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)beschrieben werden.  
  
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
|`eAbortThread`|Gibt an, dass die Common Language Runtime (CLR) den Thread ordnungsgemäß abbrechen soll. Ein ordnungsgemäßer Abbruch umfasst den Versuch, alle `finally` Blöcke, alle `catch` Blöcke im Zusammenhang mit Thread Abbrüchen und Finalizern auszuführen.|  
|`eDisableRuntime`|Gibt an, dass die CLR einen deaktivierten Zustand aufweisen soll. Im betroffenen Prozess kann kein weiterer verwalteter Code ausgeführt werden, und Threads können nicht in die CLR-Datei eingegeben werden.|  
|`eExitProcess`|Gibt an, dass die CLR eine ordnungsgemäße Beendigung des Prozesses versuchen soll, einschließlich der Ausführung von Finalizern und der Ausführung von Bereinigung-und Protokollierungs Vorgängen.|  
|`eFastExitProcess`|Gibt an, dass die CLR den Prozess sofort beenden soll, ohne Finalizer auszuführen oder Bereinigungs-und Protokollierungs Vorgänge auszuführen. Die Benachrichtigung wird jedoch an den Debugger gesendet.|  
|`eNoAction`|Gibt an, dass keine Aktion ausgeführt werden soll.|  
|`eRudeAbortThread`|Gibt an, dass die CLR einen unhöflichen Thread Abbruch ausführen soll. Nur die `catch` und `finally` Blöcke, die mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> gekennzeichnet sind, werden ausgeführt.|  
|`eRudeExitProcess`|Gibt an, dass die CLR den Prozess beenden soll, ohne Finalizer oder Protokollierungs Vorgänge ausführen zu müssen.|  
|`eRudeUnloadAppDomain`|Gibt an, dass die CLR eine unhöfliche Entladung des <xref:System.AppDomain>ausführen soll. Nur Finalizer, die mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> gekennzeichnet sind, werden ausgeführt. Ebenso erhalten alle Threads mit diesem <xref:System.AppDomain> in Ihrem Stapel eine `ThreadAbortException`, aber nur die `catch` und `finally` Blöcke, die mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> gekennzeichnet sind, werden ausgeführt.|  
|`eThrowException`|Gibt an, dass eine für die Bedingung geeignete Ausnahme, z. b. nicht genügend Arbeitsspeicher, Pufferüberlauf usw., ausgelöst werden soll.|  
|`eUnloadAppDomain`|Gibt an, dass die <xref:System.AppDomain> entladen werden soll. Die CLR versucht, Finalizer auszuführen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host legt Richtlinien Aktionen durch Aufrufen von Methoden der [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) -Schnittstelle fest. Informationen über grobe und ordnungsgemäße Abbrüche finden Sie in der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) -Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
