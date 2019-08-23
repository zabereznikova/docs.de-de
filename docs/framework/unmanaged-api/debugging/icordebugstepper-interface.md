---
title: ICorDebugStepper-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c57b13b05522614ff066b93cb9f6a437cb340576
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962684"
---
# <a name="icordebugstepper-interface"></a>ICorDebugStepper-Schnittstelle
Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Deactivate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Dies `ICorDebugStepper` bewirkt, dass der letzte Schritt Befehl abgebrochen wird.|  
|[IsActive-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Ruft einen Wert ab, der angibt `ICorDebugStepper` , ob dieser gerade einen Schritt ausführt.|  
|[SetInterceptMask-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Legt einen CorDebugIntercept-Wert fest, der die Typen von Code angibt, die in Einzelschritten werden.|  
|[SetRangeIL-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) Argument Werte in Bezug auf den systemeigenen Code oder den MSIL-Code (Microsoft Intermediate Language) der Methode übergeben, die durchlaufen wird.|  
|[SetUnmappedStopMask-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Legt einen CorDebugUnmappedStop-Wert fest, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.|  
|[Step-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Bewirkt, `ICorDebugStepper` dass dieser den enthaltenden Thread schrittweise durchläuft, und optional, um die Einzelschritt Weise durch Funktionen fortzusetzen, die innerhalb des Threads aufgerufen werden.|  
|[StepOut-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Bewirkt, `ICorDebugStepper` dass dieser den enthaltenden Thread in einem Schritt durchläuft und fertiggestellt wird, wenn der aktuelle Frame die Steuerung an den aufrufenden Frame zurückgibt.|  
|[StepRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Bewirkt, `ICorDebugStepper` dass dieser den enthaltenden Thread in einen Schritt einschlägt und zurückgibt, wenn er Code über den letzten der angegebenen Bereiche hinaus erreicht.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugStepper` -Schnittstelle dient folgenden Zwecken:  
  
- Er fungiert als Bezeichner zwischen einem ausgegebene Schritt Befehl und dem Abschluss dieses Befehls.  
  
- Sie stellt eine zentrale Schnittstelle zum Kapseln der gesamten schrittweise bereit, die ausgeführt werden können.  
  
- Es bietet eine Möglichkeit, einen schrittweise Abbruch abzubrechen.  
  
 Pro Thread kann mehr als ein Stepper vorhanden sein. Beispielsweise kann ein Haltepunkt beim Durchlaufen einer Funktion gedrückt werden, und der Benutzer möchte einen neuen Schritt Vorgang innerhalb dieser Funktion starten. Der Debugger kann feststellen, wie diese Situation behandelt werden soll. Der Debugger kann den ursprünglichen Schritt Vorgang abbrechen oder die beiden Vorgänge schachteln. Die `ICorDebugStepper` -Schnittstelle unterstützt beide Optionen.  
  
 Ein Stepper kann zwischen Threads migriert werden, wenn die Common Language Runtime (CLR) einen Thread übergreifenden, gemarshallten Aufrufvorgang durchführt.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
