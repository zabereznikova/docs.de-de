---
title: ICorDebugStepper Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper
helpviewer_keywords: ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 83d394669270eb26b33e084b20a621e18b5b14aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepper-interface1"></a>ICorDebugStepper Schnittstelle1
Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Deactivate-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|Bewirkt, dass `ICorDebugStepper` mit dem letzten Schrittbefehl Abbrechen sie empfangen.|  
|[IsActive-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|Ruft einen Wert, der angibt, ob dies `ICorDebugStepper` wird derzeit von einem Schritt ausgeführt.|  
|[SetInterceptMask-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|Legt einen CorDebugIntercept-Wert, der angibt, die Typen von Code, der durchlaufen werden.|  
|[SetRangeIL-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|Legt einen Wert, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) übergeben Argumentwerte relativ zu den systemeigenen Code oder Microsoft intermediate Language (MSIL)-Code der Methode, die schrittweise durchlaufen wird.|  
|[SetUnmappedStopMask-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|Legt einen CorDebugUnmappedStop-Wert, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.|  
|[Step-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|Bewirkt, dass `ICorDebugStepper` , Schritt für Schritt durch den enthaltenden Thread und optional zu fortfahren schrittweises Durchlaufen von Funktionen, die in dem Thread aufgerufen werden.|  
|[StepOut-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|Bewirkt, dass `ICorDebugStepper` einstufiger über den enthaltenden Thread und beendet wird, wenn der aktuelle Rahmen ist die Steuerung an den aufrufenden Rahmen zurückgibt.|  
|[StepRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|Bewirkt, dass `ICorDebugStepper` , Schritt für Schritt durch den enthaltenden Thread und zurückzugeben, wenn er Code nach dem letzten von der angegebenen Bereiche erreicht hat.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugStepper` Schnittstelle dient den folgenden Zwecken:  
  
-   Sie fungiert als Bezeichner zwischen ein Schrittbefehl, der ausgegeben wird und dem Abschluss dieses Befehls.  
  
-   Es bietet eine zentrale Schnittstelle zum kapseln alle schrittweise ausgeführt werden kann.  
  
-   Es bietet eine Möglichkeit, einer schrittweisen Ausführung vorzeitig abbrechen.  
  
 Es können mehrere zugeordnetem pro Thread vorhanden sein. Beispielsweise kann ein Haltepunkt erreicht werden, während bei einem Prozedurschritt für eine Funktion, und der Benutzer eine neue schrittweisen Ausführung innerhalb der Funktion starten möchten. Es liegt im Ermessen des Debuggers bestimmen, wie diese Situation zu behandeln. Der Debugger möchte der ursprünglichen schrittweisen Ausführung abbrechen oder die zwei Vorgänge schachteln. Die `ICorDebugStepper` Schnittstelle unterstützt beide Optionen.  
  
 Eine zugeordnetem kann zwischen Threads migriert werden, wenn die common Language Runtime (CLR) eine threadübergreifend, gemarshallte aufruft.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
