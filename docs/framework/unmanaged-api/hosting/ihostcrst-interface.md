---
title: IHostCrst-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804900"
---
# <a name="ihostcrst-interface"></a>IHostCrst-Schnittstelle
Dient als Host Darstellung eines kritischen Abschnitts zum Threading.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Enter-Methode](ihostcrst-enter-method.md)|Wechselt in den kritischen Abschnitt.|  
|[Leave-Methode](ihostcrst-leave-method.md)|Verlässt den kritischen Abschnitt.|  
|[SetSpinCount-Methode](ihostcrst-setspincount-method.md)|Legt die drehanzahl für den kritischen Abschnitt fest.|  
|[TryEnter-Methode](ihostcrst-tryenter-method.md)|Versucht, den kritischen Abschnitt einzugeben, und meldet einen Erfolg oder Fehler sofort.|  
  
## <a name="remarks"></a>Hinweise  
 `IHostCrst`ermöglicht dem Common Language Runtime (CLR), direkt mit der Darstellung eines kritischen Abschnitts des Hosts zu kommunizieren, anstatt Win32-Funktionen wie oder zu `EnterCriticalSection` verwenden `LeaveCriticalSection` .  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRSyncManager-Schnittstelle](iclrsyncmanager-interface.md)
- [IHostSyncManager-Schnittstelle](ihostsyncmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
