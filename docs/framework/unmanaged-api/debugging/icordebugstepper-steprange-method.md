---
title: ICorDebugStepper::StepRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72a68000691dd23a55b77265cae839bea8b4ae1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange-Methode
Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenden Thread und zurückgibt, wenn er Code nach dem letzten von der angegebenen Bereiche erreicht hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bStepIn`  
 [in] Legen Sie auf `true` Einzelschritt auf eine Funktion, die in dem Thread aufgerufen wird. Legen Sie auf `false` der Funktion zu überspringen.  
  
 `ranges`  
 [in] Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.  
  
 `cRangeCount`  
 [in] Die Größe des `ranges`-Arrays.  
  
## <a name="remarks"></a>Hinweise  
 Die `StepRange` -Methode funktioniert wie die [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) -Methode, außer dass es nicht bis Code außerhalb des angegebenen Bereichs abgeschlossen wird erreicht ist.  
  
 Dies kann effizienter als die schrittweise Ausführung einer Anweisung zu einem Zeitpunkt sein. Bereiche werden als eine Liste von Endoffsetpaaren ab dem Anfang der zugeordnetem Frame angegeben.  
  
 Bereiche sind relativ zu der Microsoft intermediate Language (MSIL)-Code einer Methode. Rufen Sie [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) mit `false` auf die Bereiche relativ systemeigenem Code einer Methode zu machen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
