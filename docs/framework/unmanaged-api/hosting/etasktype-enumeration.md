---
title: ETaskType-Enumeration
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
ms.openlocfilehash: 332488fee4c982fdbaecceeaa2a6a3876f1602a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733697"
---
# <a name="etasktype-enumeration"></a>ETaskType-Enumeration

Enthält Werte, die den Typ der Aufgabe angeben, die durch eine [ICLRTask](iclrtask-interface.md) -oder [IHostTask](ihosttask-interface.md) -Schnittstelle dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`TT_ADUNLOAD`|Die-Schnittstelle stellt eine Aufgabe zum Entladen einer Anwendungsdomäne dar.|  
|`TT_DEBUGGERHELPER`|Die-Schnittstelle stellt eine Debugger-hilfsaufgabe dar.|  
|`TT_FINALIZER`|Die-Schnittstelle stellt eine Finalizer-Aufgabe dar.|  
|`TT_GC`|Die-Schnittstelle stellt eine Garbage Collection Aufgabe dar.|  
|`TT_THREADPOOL_GATE`|Die-Schnittstelle stellt eine Gate-Thread Aufgabe dar.|  
|`TT_THREADPOOL_IOCOMPLETION`|Die-Schnittstelle stellt eine e/a-Thread Aufgabe oder einen Beendigungs Port-Thread Task dar.|  
|`TT_THREADPOOL_TIMER`|Die-Schnittstelle stellt eine Zeit Geber Thread Aufgabe dar.|  
|`TT_THREADPOOL_WAIT`|Die-Schnittstelle stellt eine warte Thread Aufgabe dar.|  
|`TT_THREADPOOL_WORKER`|Die-Schnittstelle stellt eine Arbeits Thread Aufgabe dar.|  
|`TT_UNKNOWN`|Der Task ist unbekannt.|  
|`TT_USER`|Die-Schnittstelle stellt eine Benutzer Aufgabe dar.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Enumerationen](hosting-enumerations.md)
