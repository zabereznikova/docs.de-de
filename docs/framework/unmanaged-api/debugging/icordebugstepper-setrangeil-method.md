---
title: ICorDebugStepper::SetRangeIL-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 7fadffaab6eee5beed513f339ea300acef5a1c6b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378991"
---
# <a name="icordebugsteppersetrangeil-method"></a>ICorDebugStepper::SetRangeIL-Methode
Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) Argument Werte übergeben, die relativ zum systemeigenen Code oder relativ zum MSIL-Code (Microsoft Intermediate Language) der Methode sind, die durchlaufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bIL`  
 in Legen Sie auf fest, `true` um anzugeben, dass die Bereiche mit dem MSIL-Code relativ sind. Legen Sie auf fest, `false` um anzugeben, dass die Bereiche relativ zum systemeigenen Code sind. Der Standardwert ist `true`.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
