---
title: IGCThreadControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 78e667acf1573769a1a67b4c964d7801f11838fe
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805130"
---
# <a name="igcthreadcontrol-interface"></a>IGCThreadControl-Schnittstelle
Stellt Methoden für die Teilnahme an der Planung von Threads bereit, die andernfalls für eine Garbage Collection blockiert werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SuspensionEnding-Methode](igcthreadcontrol-suspensionending-method.md)|Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.|  
|[SuspensionStarting-Methode](igcthreadcontrol-suspensionstarting-method.md)|Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.|  
|[ThreadIsBlockingForSuspension-Methode](igcthreadcontrol-threadisblockingforsuspension-method.md)|Benachrichtigt den Host, dass der Thread, der den-anfordert, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hostingschnittstellen](hosting-interfaces.md)
