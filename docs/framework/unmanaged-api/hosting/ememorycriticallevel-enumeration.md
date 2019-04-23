---
title: EMemoryCriticalLevel-Enumeration
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ee8705d00e1f63f69863d0bf8e7d0d9d62807e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122290"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel-Enumeration
Enthält Werte, die die Auswirkungen eines Fehlers angeben, wenn eine bestimmte speicherbelegung angefordert wurde, aber nicht zufrieden.  
  
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
|`eAppDomainCritical`|Gibt an, dass die Zuordnung ist wichtig für die Ausführung von verwaltetem Code in der Domäne, die die Zuordnung angefordert hat. Wenn Arbeitsspeicher zugeordnet werden kann, kann nicht die CLR nicht garantieren, dass die Domäne noch verwendbar ist. Der Host entscheidet, welche Aktion soll, wenn die Zuordnung nicht erfüllt werden kann. Sie können die CLR anweisen, zum Abbrechen der `AppDomain` automatisch, oder lassen sie Sie weiterhin ausgeführt, durch Aufrufen von Methoden für [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code im Prozess wichtig ist. Dieser Wert wird während des Starts und bei der Ausführung von Finalizern verwendet. Wenn der Arbeitsspeicher nicht reserviert werden kann, kann nicht die CLR im Prozess ausgeführt werden. Wenn die Zuordnung fehlschlägt, wird die CLR deaktiviert. Alle nachfolgenden Aufrufe in die CLR schlagen mit HOST_E_CLRNOTAVAILABLE zurück.|  
|`eTaskCritical`|Gibt an, dass die Zuordnung ist entscheidend für die Ausführung des Tasks, die die Zuordnung angefordert hat. Wenn Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht gewährleisten, dass die Aufgabe ausgeführt werden kann. Bei einem Fehler löst die CLR eine <xref:System.Threading.ThreadAbortException> auf dem physischen Betriebssystemthread.|  
  
## <a name="remarks"></a>Hinweise  
 Die Speicher-Zuordnung in definierten Methoden den [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) und [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) Schnittstellen akzeptieren einen Parameter dieses Typs. Abhängig vom Schweregrad des Fehlers, kann ein Host entscheiden Sie, ob die zuordnungsanforderung sofort fehl, oder warten, bis es erfüllt werden kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRMemoryNotificationCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
