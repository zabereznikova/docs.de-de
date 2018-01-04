---
title: EPolicyAction-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de55d46eead37962fad7d7c1c5bd1766e772fe8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction-Enumeration
Beschreibt die für Richtlinienaktionen, die der Host kann für Vorgänge, die durch beschrieben festlegen [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) und durch beschriebene Fehler [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`eAbortThread`|Gibt an, dass die common Language Runtime (CLR) des Threads ordnungsgemäß abgebrochen werden soll. Ein ordnungsgemäßer Abbruch beinhaltet den Versuch, führen Sie alle `finally` Blöcke, alle `catch` Blöcke im Zusammenhang mit Threadabbrüche und Finalizer.|  
|`eDisableRuntime`|Gibt an, dass die CLR einen deaktivierten Zustand eingeben sollte. Keine weiteren verwalteter Code in den betroffenen Prozess ausgeführt werden kann, und der CLR Threads blockiert.|  
|`eExitProcess`|Gibt an, dass die CLR dem ordnungsgemäßen Beenden des Prozesses, einschließlich der Ausführung von Finalizern und Bereinigung und protokollieren soll.|  
|`eFastExitProcess`|Gibt an, dass die CLR den Prozess sofort beendet, sollten ohne Ausführung von Finalizern oder Bereinigung und Vorgänge. Jedoch ein Benachrichtigung wird an den Debugger gesendet werden.|  
|`eNoAction`|Gibt an, dass keine Aktion ausgeführt werden soll.|  
|`eRudeAbortThread`|Gibt an, dass die CLR eine grobe Threadabbruchs durchführen soll. Nur die `catch` und `finally` Blöcke gekennzeichnet mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.|  
|`eRudeExitProcess`|Gibt an, dass die CLR den Prozess beendet werden soll, ohne Ausführung von Finalizern oder wenn die Protokollierung von Vorgängen.|  
|`eRudeUnloadAppDomain`|Gibt an, dass die CLR ein grobe Entladen durchführen soll die <xref:System.AppDomain>. Nur Finalizer mit markierten <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden. Auf ähnliche Weise alle Threads mit dieser <xref:System.AppDomain> im Stapel Empfangen einer `ThreadAbortException`, sondern nur die `catch` und `finally` Blöcke gekennzeichnet mit <xref:System.EnterpriseServices.MustRunInClientContextAttribute> ausgeführt werden.|  
|`eThrowException`|Gibt an, dass eine Ausnahme, die die Bedingung, z. B. Out of Memory, Pufferüberlauf usw., ausgelöst werden soll.|  
|`eUnloadAppDomain`|Gibt an, dass die <xref:System.AppDomain> entladen werden soll. Die CLR versucht, Finalizer auszuführen.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host Richtlinienaktionen festgelegt, durch Aufrufen von Methoden des der [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) Schnittstelle. Informationen über grobe und ordnungsgemäßes Abbrüche finden Sie unter der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [EClrFailure-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [ICLRPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
