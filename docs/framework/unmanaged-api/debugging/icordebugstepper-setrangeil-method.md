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
ms.openlocfilehash: b3153a88867d249aad8365bb774348fb8c9d57d5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791749"
---
# <a name="icordebugsteppersetrangeil-method"></a>ICorDebugStepper::SetRangeIL-Methode
Legt einen Wert fest, der angibt, ob Aufrufe von [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) Argument Werte übergeben, die relativ zum systemeigenen Code oder relativ zum MSIL-Code (Microsoft Intermediate Language) der Methode sind, die durchlaufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `bIL`  
 in Legen Sie diese Einstellung auf `true` fest, um anzugeben, dass die Bereiche mit dem MSIL-Code relativ sind. Legen Sie diese Einstellung auf `false` fest, um anzugeben, dass die Bereiche relativ zum systemeigenen Code sind. Der Standardwert ist `true`sein.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
