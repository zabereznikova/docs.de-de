---
title: ICorDebugStepper::StepRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ace501bf5de741ea110fe4d3bb4bc44843bf8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760538"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange-Methode
Bewirkt, dass dieser ICorDebugStepper, Schritt für Schritt durch den enthaltenen Thread bis zum zurückgeben, wenn sie den Code nach dem letzten von der angegebenen Bereiche erreicht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bStepIn`  
 [in] Legen Sie auf `true` um einen Einzelschritt für eine Funktion, die den Thread aufgerufen wird. Legen Sie auf `false` der Funktion zu überspringen.  
  
 `ranges`  
 [in] Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.  
  
 `cRangeCount`  
 [in] Die Größe des `ranges`-Arrays.  
  
## <a name="remarks"></a>Hinweise  
 Die `StepRange` -Methode funktioniert wie die [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) -Methode, mit dem Unterschied, dass sie nicht bis zum Code außerhalb des angegebenen Bereichs abgeschlossen wird erreicht ist.  
  
 Dies kann effizienter als die schrittweise Ausführung einer Anweisung zu einem Zeitpunkt sein. Bereiche werden als eine Liste von Endoffsetpaaren ab dem Anfang der zugeordnetem des Frames angegeben.  
  
 Bereiche sind relativ zu der Microsoft intermediate Language (MSIL)-Code einer Methode. Rufen Sie [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) mit `false` um die Bereiche relativ zu den systemeigenen Code einer Methode machen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
