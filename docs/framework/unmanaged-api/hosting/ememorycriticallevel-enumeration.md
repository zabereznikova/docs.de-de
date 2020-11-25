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
ms.openlocfilehash: 3b9ad4b40ce94420f2ab5fc25335c41dec15dc09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720551"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel-Enumeration

Enthält Werte, die die Auswirkung eines Fehlers angeben, wenn eine bestimmte Speicher Belegung angefordert wurde, jedoch nicht erfüllt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`eAppDomainCritical`|Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code in der Domäne, die die Zuordnung angefordert hat, wichtig ist. Wenn kein Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht sicherstellen, dass die Domäne weiterhin verwendbar ist. Der Host entscheidet, welche Aktion ausgeführt werden soll, wenn die Zuordnung nicht erfüllt werden kann. Sie kann die CLR anweisen, den automatisch abzubrechen `AppDomain` , oder die Ausführung durch Aufrufen von Methoden für [ICLRPolicyManager](iclrpolicymanager-interface.md)fortsetzen lassen.|  
|`eProcessCritical`|Gibt an, dass die Zuordnung für die Ausführung von verwaltetem Code im Prozess wichtig ist. Dieser Wert wird beim Start und beim Ausführen von Finalizern verwendet. Wenn kein Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht in diesem Prozess ausgeführt werden. Wenn die Zuordnung fehlschlägt, wird die CLR effektiv deaktiviert. Alle nachfolgenden Aufrufe der CLR schlagen mit HOST_E_CLRNOTAVAILABLE fehl.|  
|`eTaskCritical`|Gibt an, dass die Zuordnung für die Ausführung der Aufgabe, die die Zuordnung angefordert hat, wichtig ist. Wenn kein Arbeitsspeicher zugeordnet werden kann, kann die CLR nicht garantieren, dass der Task ausgeführt werden kann. Im Fall eines Fehlers löst die CLR eine <xref:System.Threading.ThreadAbortException> auf dem physischen Vorgangs System Thread aus.|  
  
## <a name="remarks"></a>Hinweise  

 Die in den Schnittstellen [IHostMemoryManager](ihostmemorymanager-interface.md) und [IHostMAlloc](ihostmalloc-interface.md) definierten Speicher Belegungs Methoden akzeptieren einen Parameter dieses Typs. Je nach Schweregrad eines Fehlers kann ein Host entscheiden, ob die Zuordnungs Anforderung sofort fehlschlagen soll oder ob gewartet werden kann, bis Sie erfüllt ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRMemoryNotificationCallback-Schnittstelle](iclrmemorynotificationcallback-interface.md)
- [Hosten von Enumerationen](hosting-enumerations.md)
