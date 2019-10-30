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
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131890"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame-Schnittstelle
Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugRuntimeUnwindableFrame` ist eine spezialisierte Version der ICorDebugFrame-Schnittstelle. Sie wird von nicht verwalteten Methoden verwendet, die erfordern, dass die Laufzeit einen Frame auf dem aktuellen Stapel lädt. Vorhandene Entwicklungs Konventionen funktionieren nicht, da Sie keinen JIT-kompilierten Code verwenden. Wenn der Debugger einen nicht abzurufbaren Frame erkennt, sollte er die [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) -Methode verwenden, um ihn zu entladen, aber er sollte die Überprüfung selbst durchführen. Wenn der Debugger eine `ICorDebugRuntimeUnwindableFrame`empfängt, kann er die [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) -Methode aufrufen, um den Kontext des Frames abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
