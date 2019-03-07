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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493023"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step-Methode
Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenen Thread und (optional) um fortzufahren, schrittweises Durchlaufen von Funktionen, in dem Thread aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bStepIn`  
 [in] Legen Sie auf `true` um einen Einzelschritt für eine Funktion, die den Thread aufgerufen wird. Legen Sie auf `false` der Funktion zu überspringen.  
  
## <a name="remarks"></a>Hinweise  
 Der Schritt abgeschlossen ist, wenn die common Language Runtime die nächste verwaltete Anweisung in diesem zugeordnetem des Frames ausführt. Wenn `Step` ist für eine zugeordnetem aufgerufen, die nicht von verwaltetem Code, der Schritt abgeschlossen, wenn die nächste Anweisung verwalteten Code von der Thread ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
