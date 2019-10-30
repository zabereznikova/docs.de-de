---
title: ICorDebugController::Detach-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: b98077914d680c908587649fdd517aca9c8dcd40
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125433"
---
# <a name="icordebugcontrollerdetach-method"></a>ICorDebugController::Detach-Methode
Trennt den Debugger vom Prozess oder der Anwendungsdomäne.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Prozess oder die Anwendungsdomäne wird normal ausgeführt, aber das Objekt "ICorDebugProcess" oder "ICorDebugAppDomain" ist nicht mehr gültig, und es werden keine weiteren Rückrufe mehr angezeigt.  
  
 Wenn in der .NET Framework Version 2,0 die Option nicht verwaltetes Debuggen aktiviert ist, tritt bei dieser Methode ein Fehler aufgrund von Einschränkungen des Betriebssystems auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
