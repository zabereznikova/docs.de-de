---
title: ICorDebugRuntimeUnwindableFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f006085aba140264e2a2605adce39924dbe082e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568113"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame-Schnittstelle
Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugRuntimeUnwindableFrame` ist eine spezialisierte Version der ICorDebugFrame-Schnittstelle. Es wird von nicht verwalteten Methoden verwendet, die die Laufzeit Entladen eines Frames auf dem aktuellen Stapel erfordern. Vorhandene Entladung Konventionen funktionieren nicht, da keine JIT-kompiliertem Code verwendet wird. Wenn der Debugger einen entladbaren Frame erkennt, muss bei Verwendung der [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) Methode entladen, aber sie sollten die Überprüfung selbst durchführen. Wenn der Debugger empfängt eine `ICorDebugRuntimeUnwindableFrame`, Aufrufen der [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode zum Abrufen des Kontexts des Frames.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
