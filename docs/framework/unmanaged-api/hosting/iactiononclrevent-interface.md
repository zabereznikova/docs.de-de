---
title: IActionOnCLREvent-Schnittstelle
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: f577e9252d97ec188ff1076fd8340336b16c8257
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504328"
---
# <a name="iactiononclrevent-interface"></a>IActionOnCLREvent-Schnittstelle
Stellt die [iaktiononclrevent:: OnEvent](iactiononclrevent-onevent-method.md) -Methode bereit, die Rückrufe für Ereignisse ausführt, die mit einem Aufruf der [ICLROnEventManager:: registeraktiononevent](iclroneventmanager-registeractiononevent-method.md) -Methode registriert wurden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[OnEvent-Methode](iactiononclrevent-onevent-method.md)|Führt einen Rückruf für ein registriertes Ereignis aus.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [EClrEvent-Enumeration](eclrevent-enumeration.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICLROnEventManager-Schnittstelle](iclroneventmanager-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
