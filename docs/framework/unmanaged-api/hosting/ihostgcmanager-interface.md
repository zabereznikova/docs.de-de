---
title: IHostGCManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804853"
---
# <a name="ihostgcmanager-interface"></a>IHostGCManager-Schnittstelle
Stellt Methoden bereit, die den Host von Ereignissen in dem Garbage Collection Mechanismus benachrichtigen, der vom Common Language Runtime (CLR) implementiert wird.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[SuspensionEnding-Methode](ihostgcmanager-suspensionending-method.md)|Benachrichtigt den Host, dass die CLR die Ausführung von Tasks auf Threads fortsetzt, die für eine Garbage Collection angehalten wurden.|  
|[SuspensionStarting-Methode](ihostgcmanager-suspensionstarting-method.md)|Benachrichtigt den Host, dass die CLR die Ausführung von Tasks unterteilt, um eine Garbage Collection auszuführen.|  
|[ThreadIsBlockingForSuspension-Methode](ihostgcmanager-threadisblockingforsuspension-method.md)|Benachrichtigt den Host, dass der Thread, von dem der Methoden aufrufging, für eine Garbage Collection blockiert wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRTask-Schnittstelle](iclrtask-interface.md)
- [ICLRTaskManager-Schnittstelle](iclrtaskmanager-interface.md)
- [IHostTask-Schnittstelle](ihosttask-interface.md)
- [IHostTaskManager-Schnittstelle](ihosttaskmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
