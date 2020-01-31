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
ms.openlocfilehash: 21b8bf618e197372e301d5f56e7592c20710014d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791713"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange-Methode
Bewirkt, dass ICorDebugStepper den enthaltenden Thread mit einem einzelnen Schritt durchläuft und zurückgegeben wird, wenn er Code über den letzten der angegebenen Bereiche hinaus erreicht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `bStepIn`  
 in Legen Sie auf `true`, um eine im Thread aufgerufene Funktion schrittweise zu durchlaufen. Legen Sie auf `false`, um die Funktion zu überspringen.  
  
 `ranges`  
 in Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.  
  
 `cRangeCount`  
 [in] Die Größe des `ranges`-Arrays.  
  
## <a name="remarks"></a>Hinweise  
 Die `StepRange`-Methode funktioniert wie die [ICorDebugStepper:: Step](icordebugstepper-step-method.md) -Methode, mit dem Unterschied, dass Sie erst ausgeführt wird, wenn der Code außerhalb des angegebenen Bereichs erreicht wird.  
  
 Dies kann effizienter sein als die Schritt-für-Schritt-Anleitung für eine Anweisung. Bereiche werden als Liste der Offset Paare ab dem Anfang des Frame Bilds angegeben.  
  
 Bereiche sind relativ zum MSIL-Code (Microsoft Intermediate Language) einer Methode. Aufrufen von [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) mit `false`, um die Bereiche relativ zum systemeigenen Code einer Methode zu machen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
