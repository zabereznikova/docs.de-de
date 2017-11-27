---
title: EMemoryCriticalLevel-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryCriticalLevel
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryCriticalLevel
helpviewer_keywords: EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b15a6786cb99a64d441d7e05fb91cd8ff0f3af92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel-Enumeration
Enthält Werte, die die Auswirkungen eines Ausfalls angeben, wenn eine bestimmte speicherbelegung angefordert wurde, jedoch nicht erfüllt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`eAppDomainCritical`|Gibt an, dass die Zuordnung ist wichtig für die Ausführung von verwaltetem Code in der Domäne, die die Belegung angefordert hat. Wenn Speicher belegt werden kann, kann nicht die CLR zu gewährleisten, dass die Domäne immer noch verwendbar ist. Der Host entscheidet, welche Aktion soll, wenn die Zuordnung nicht erfüllt werden kann. Sie können die CLR anweisen der `AppDomain` automatisch, oder lassen sie Sie weiterhin ausgeführt, durch Aufrufen von Methoden für [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code im Prozess von entscheidender Bedeutung ist. Dieser Wert wird während des Starts und verwendet, wenn ein Finalizer ausgeführt wird. Wenn Speicher belegt werden kann, kann nicht die CLR im Prozess ausgeführt werden. Wenn die Zuordnung ein Fehler auftritt, ist die CLR effektiv deaktiviert. Alle nachfolgenden Aufrufe in die CLR schlagen mit HOST_E_CLRNOTAVAILABLE fehl.|  
|`eTaskCritical`|Gibt an, dass die Zuordnung ist wichtig für die Ausführung der Aufgabe, die die Belegung angefordert hat. Wenn Speicher belegt werden kann, kann nicht die CLR zu gewährleisten, dass die Aufgabe ausgeführt werden kann. Fehler auftritt, löst die CLR eine <xref:System.Threading.ThreadAbortException> auf dem physischen Betriebssystemthread.|  
  
## <a name="remarks"></a>Hinweise  
 Die Arbeitsspeicher-Zuordnung in definierten Methoden den [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) und [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) Schnittstellen akzeptieren einen Parameter dieses Typs. Abhängig vom Schweregrad des Fehlers, kann ein Host entscheiden Sie, ob die zuordnungsanforderung sofort fehl, oder warten, bis er erfüllt werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRMemoryNotificationCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
