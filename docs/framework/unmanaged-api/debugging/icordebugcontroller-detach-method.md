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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f2dae147f8667a73036dbcf873e2082996b2755
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666984"
---
# <a name="icordebugcontrollerdetach-method"></a>ICorDebugController::Detach-Methode
Trennt den Debugger aus der Domäne Prozess- oder Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Prozess oder eine Anwendung weiterhin ordnungsgemäß, aber das "ICorDebugProcess" oder "ICorDebugAppDomain"-Objekt ist nicht mehr gültig und keine weiteren Rückrufe ausgeführt werden.  
  
 Wenn nicht verwaltetes debugging aktiviert ist, wird diese Methode in .NET Framework, Version 2.0 aufgrund von Beschränkungen im Betriebssystem fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

