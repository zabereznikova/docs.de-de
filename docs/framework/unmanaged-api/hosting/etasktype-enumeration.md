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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59fdc3d4682fe3c1967c8153043dc1bfe0668c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610538"
---
# <a name="etasktype-enumeration"></a>ETaskType-Enumeration
Enthält Werte, die den Typ der Aufgabe angeben, indem Sie entweder dargestellt wird, ein [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) oder [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
|Member|Beschreibung|  
|------------|-----------------|  
|`TT_ADUNLOAD`|Die Schnittstelle stellt eine Aufgabe zur Entladung einer Anwendung dar.|  
|`TT_DEBUGGERHELPER`|Die Schnittstelle stellt einen Debugger-Hilfsprogramm-Task dar.|  
|`TT_FINALIZER`|Die Schnittstelle stellt einen Finalizer-Task dar.|  
|`TT_GC`|Die Schnittstelle stellt eine Garbage Collection-Aufgabe dar.|  
|`TT_THREADPOOL_GATE`|Die Schnittstelle stellt einen Gate-Thread-Task dar.|  
|`TT_THREADPOOL_IOCOMPLETION`|Die Schnittstelle stellt eine e/a-Thread-Aufgabe oder Thread eine Abschlussaufgabe-Port dar.|  
|`TT_THREADPOOL_TIMER`|Die Schnittstelle stellt einen Timer-Thread-Task dar.|  
|`TT_THREADPOOL_WAIT`|Die Schnittstelle stellt einen Wait-Thread-Task dar.|  
|`TT_THREADPOOL_WORKER`|Die Schnittstelle stellt eine Aufgabe der Worker-Threads dar.|  
|`TT_UNKNOWN`|Der Task ist unbekannt.|  
|`TT_USER`|Die Schnittstelle stellt eine Aufgabe dar.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
