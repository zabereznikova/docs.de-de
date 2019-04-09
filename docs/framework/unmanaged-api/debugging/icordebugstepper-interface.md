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
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212517"
---
# <a name="icordebugstepper-interface"></a>ICorDebugStepper-Schnittstelle
Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Deactivate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Bewirkt, dass dieser `ICorDebugStepper` , mit dem letzten Schrittbefehl abzubrechen, er empfangen.|  
|[IsActive-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Ruft einen Wert, der angibt, ob dies `ICorDebugStepper` aktuell einen Schritt ausgeführt wird.|  
|[SetInterceptMask-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Legt einen CorDebugIntercept-Wert, der angibt, die Typen von Code, der durchlaufen werden.|  
|[SetRangeIL-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Legt einen Wert, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) Argumentwerte, die relativ zu den systemeigenen Code oder Code für Microsoft intermediate Language (MSIL) der Methode, die schrittweise durchlaufen wird übergeben.|  
|[SetUnmappedStopMask-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Legt einen CorDebugUnmappedStop-Wert, der den Typ von nicht zugeordnetem Code gibt an, in dem die Ausführung angehalten wird.|  
|[Step-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Bewirkt, dass dieser `ICorDebugStepper` , Schritt für Schritt durch den enthaltenen Thread und (optional) um weiterhin schrittweises Durchlaufen von Funktionen, in dem Thread aufgerufen werden.|  
|[StepOut-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Bewirkt, dass dieser `ICorDebugStepper` Schritt für Schritt durch den enthaltenen Thread und beendet wird, wenn der aktuelle Frame die steuerelementrückgabe an den aufrufenden Rahmen.|  
|[StepRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Bewirkt, dass dieser `ICorDebugStepper` , Schritt für Schritt durch den enthaltenen Thread und zurückzugeben, wenn sie Code nach dem letzten von der angegebenen Bereiche erreicht.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugStepper` -Schnittstelle dient folgenden Zwecken:  
  
-   Er fungiert als Bezeichner zwischen ein Schrittbefehl, der ausgegeben wird und dem Abschluss dieses Befehls.  
  
-   Es bietet eine zentrale Schnittstelle zum kapseln alle das schrittweise durchlaufen, die ausgeführt werden können.  
  
-   Es bietet eine Möglichkeit, einer schrittweisen Ausführung vorzeitig abbrechen.  
  
 Es können mehrere zugeordnetem pro Thread vorhanden sein. Z. B. ein Haltepunkt erreicht werden kann, während bei einem Prozedurschritt für eine Funktion, und der Benutzer eine neue schrittweisen Ausführung innerhalb dieser Funktion beginnen möchten. Es ist Aufgabe des Debuggers zu bestimmen, wie für diese Situation. Der Debugger sollten die ursprünglichen schrittweisen Ausführung abbrechen oder Schachteln von beiden Vorgänge. Die `ICorDebugStepper` Schnittstelle unterstützt beides.  
  
 Eine zugeordnetem kann zwischen Threads migrieren, wenn die common Language Runtime (CLR) Cross-Thread, gemarshallten aufruft.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
