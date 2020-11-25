---
title: ICorDebugStepper::Step-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 234705e4495a1a582f3801ad1e645f923cd6f4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727691"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step-Methode

Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft, und optional, um die Einzelschritt Weise durch Funktionen fortzusetzen, die im Thread aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `bStepIn`  
 in Legen Sie diese Einstellung auf fest, `true` um eine Funktion innerhalb des Threads zu durchlaufen. Legen Sie auf fest `false` , um die Funktion zu überspringen.  
  
## <a name="remarks"></a>Hinweise  

 Der Schritt wird ausgeführt, wenn das Common Language Runtime die nächste verwaltete Anweisung im Frame dieses Stepper ausführt. Wenn `Step` auf einem Stepper aufgerufen wird, der sich nicht in verwaltetem Code befindet, wird der Schritt abgeschlossen, wenn die nächste verwaltete Code Anweisung vom Thread ausgeführt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
