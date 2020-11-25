---
title: ICLROnEventManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 1948075d87b5a44397a1eaab3adb4edbc96d7143
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725631"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager-Schnittstelle

Stellt Methoden bereit, die es dem Host ermöglichen, Rückrufe für Common Language Runtime (CLR)-Ereignisse zu registrieren und die Registrierung aufzuheben.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[RegisterActionOnEvent-Methode](iclroneventmanager-registeractiononevent-method.md)|Registriert einen Rückruf Zeiger für das angegebene Ereignis.|  
|[UnregisterActionOnEvent-Methode](iclroneventmanager-unregisteractiononevent-method.md)|Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.|  
  
## <a name="remarks"></a>Hinweise  

 Um Ereignis Rückrufe zu registrieren und deren Registrierung aufzuheben, erhält der Host einen Verweis auf, `ICLROnEventManager` indem er die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode aufrufen.  
  
> [!NOTE]
> Die von [EClrEvent](eclrevent-enumeration.md) beschriebenen Ereignisse können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [EClrEvent-Enumeration](eclrevent-enumeration.md)
- [IActionOnCLREvent-Schnittstelle](iactiononclrevent-interface.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
