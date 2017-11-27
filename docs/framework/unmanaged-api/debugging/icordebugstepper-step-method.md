---
title: ICorDebugStepper::Step-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.Step
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 914773adefd2ed4c1aa98310fd27a0cbc829bf49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step-Methode
Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenden Thread und optional zu fortfahren schrittweises Durchlaufen von Funktionen, die in dem Thread aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bStepIn`  
 [in] Legen Sie auf `true` Einzelschritt auf eine Funktion, die in dem Thread aufgerufen wird. Legen Sie auf `false` der Funktion zu überspringen.  
  
## <a name="remarks"></a>Hinweise  
 Der Schritt abgeschlossen ist, wenn die common Language Runtime die nächste verwaltete Anweisung im Rahmen dieser zugeordnetem ausführt. Wenn `Step` ist in einem zugeordnetem aufgerufen, die nicht von verwaltetem Code, der Schritt wird ausgeführt, wenn die nächste Anweisung verwalteten Code von der Thread ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
