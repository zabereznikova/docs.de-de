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
ms.openlocfilehash: a7b0608e85411844828cebea34c0ce5ef5b1bd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379384"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame-Schnittstelle
Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugRuntimeUnwindableFrame`ist eine spezialisierte Version der ICorDebugFrame-Schnittstelle. Sie wird von nicht verwalteten Methoden verwendet, die erfordern, dass die Laufzeit einen Frame auf dem aktuellen Stapel lädt. Vorhandene Entwicklungs Konventionen funktionieren nicht, da Sie keinen JIT-kompilierten Code verwenden. Wenn der Debugger einen nicht abzurufbaren Frame erkennt, sollte er die [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) -Methode verwenden, um ihn zu entladen, aber er sollte die Überprüfung selbst durchführen. Wenn der Debugger einen empfängt `ICorDebugRuntimeUnwindableFrame` , kann er die [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) -Methode aufrufen, um den Kontext des Frames abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
