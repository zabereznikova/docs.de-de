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
ms.openlocfilehash: d9698afa2723a5d772ecf5a055f09c5ee3bc13f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727652"
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
  
## <a name="parameters"></a>Parameter  

 `bStepIn`  
 in Legen Sie diese Einstellung auf fest, `true` um eine Funktion innerhalb des Threads zu durchlaufen. Legen Sie auf fest `false` , um die Funktion zu überspringen.  
  
 `ranges`  
 in Ein Array von COR_DEBUG_STEP_RANGE-Strukturen, von denen jedes einen Bereich angibt.  
  
 `cRangeCount`  
 [in] Die Größe des `ranges`-Arrays.  
  
## <a name="remarks"></a>Hinweise  

 Die- `StepRange` Methode funktioniert wie die [ICorDebugStepper:: Step](icordebugstepper-step-method.md) -Methode, mit dem Unterschied, dass Sie nicht vervollständigt wird, bis Code außerhalb des angegebenen Bereichs erreicht wird.  
  
 Dies kann effizienter sein als die Schritt-für-Schritt-Anleitung für eine Anweisung. Bereiche werden als Liste der Offset Paare ab dem Anfang des Frame Bilds angegeben.  
  
 Bereiche sind relativ zum MSIL-Code (Microsoft Intermediate Language) einer Methode. Aufrufen von [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) mit `false` , um die Bereiche relativ zum systemeigenen Code einer Methode zu machen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
