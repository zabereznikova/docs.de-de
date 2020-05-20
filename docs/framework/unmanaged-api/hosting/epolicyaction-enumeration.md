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
ms.openlocfilehash: 8788d6e2220778a3f0926d5ed3dd59142487bcca
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616189"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction-Enumeration
Beschreibt die Richtlinien Aktionen, die der Host für Vorgänge festlegen kann, die durch [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) und Fehler beschrieben werden, die von [EClrFailure](eclrfailure-enumeration.md)beschrieben werden.  
  
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
|`eAbortThread`|Gibt an, dass die Common Language Runtime (CLR) den Thread ordnungsgemäß abbrechen soll. Ein ordnungsgemäßer Abbruch umfasst den Versuch, alle `finally` Blöcke auszuführen, alle `catch` Blöcke im Zusammenhang mit Thread Abbrüchen und Finalizern.|  
|`eDisableRuntime`|Gibt an, dass die CLR einen deaktivierten Zustand aufweisen soll. Im betroffenen Prozess kann kein weiterer verwalteter Code ausgeführt werden, und Threads können nicht in die CLR-Datei eingegeben werden.|  
|`eExitProcess`|Gibt an, dass die CLR eine ordnungsgemäße Beendigung des Prozesses versuchen soll, einschließlich der Ausführung von Finalizern und der Ausführung von Bereinigung-und Protokollierungs Vorgängen.|  
|`eFastExitProcess`|Gibt an, dass die CLR den Prozess sofort beenden soll, ohne Finalizer auszuführen oder Bereinigungs-und Protokollierungs Vorgänge auszuführen. Die Benachrichtigung wird jedoch an den Debugger gesendet.|  
|`eNoAction`|Gibt an, dass keine Aktion ausgeführt werden soll.|  
|`eRudeAbortThread`|Gibt an, dass die CLR einen unhöflichen Thread Abbruch ausführen soll. Nur diejenigen `catch` und `finally` Blöcke, die mit markiert <xref:System.EnterpriseServices.MustRunInClientContextAttribute> sind, werden ausgeführt.|  
|`eRudeExitProcess`|Gibt an, dass die CLR den Prozess beenden soll, ohne Finalizer oder Protokollierungs Vorgänge ausführen zu müssen.|  
|`eRudeUnloadAppDomain`|Gibt an, dass die CLR eine unhöfliche Entladung des ausführen soll <xref:System.AppDomain> . Nur mit markierte Finalizer <xref:System.EnterpriseServices.MustRunInClientContextAttribute> werden ausgeführt. Ebenso empfangen alle Threads mit diesem <xref:System.AppDomain> in Ihrem Stapel eine `ThreadAbortException` , aber nur die `catch` `finally` mit markierten Blöcke <xref:System.EnterpriseServices.MustRunInClientContextAttribute> werden ausgeführt.|  
|`eThrowException`|Gibt an, dass eine für die Bedingung geeignete Ausnahme, z. b. nicht genügend Arbeitsspeicher, Pufferüberlauf usw., ausgelöst werden soll.|  
|`eUnloadAppDomain`|Gibt an, dass das <xref:System.AppDomain> entladen werden soll. Die CLR versucht, Finalizer auszuführen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host legt Richtlinien Aktionen durch Aufrufen von Methoden der [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) -Schnittstelle fest. Informationen über grobe und ordnungsgemäße Abbrüche finden Sie in der [EClrOperation](eclroperation-enumeration.md) -Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [EClrFailure-Enumeration](eclrfailure-enumeration.md)
- [ICLRPolicyManager-Schnittstelle](iclrpolicymanager-interface.md)
- [IHostPolicyManager-Schnittstelle](ihostpolicymanager-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
