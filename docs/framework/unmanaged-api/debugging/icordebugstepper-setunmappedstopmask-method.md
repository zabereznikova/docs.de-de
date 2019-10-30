---
title: ICorDebugStepper::SetUnmappedStopMask-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: ff393b119c349e34898b781c3185cc82f2dba11f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137549"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask-Methode
Legt einen Wert fest, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mask`  
 in Ein Wert der CorDebugUnmappedStop-Enumeration, der den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung stoppt.  
  
 Der Standardwert ist STOP_OTHER_UNMAPPED. Der Wert STOP_UNMANAGED ist nur beim Interop-Debuggen gültig.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Debugger eine Just-in-time (JIT)-Kompilierung findet, die keine entsprechende Zuordnung zur Microsoft Intermediate Language (MSIL) aufweist, wird die Ausführung angehalten, wenn das Flag, das den Typ des nicht zugeordneten Codes angibt, festgelegt wurde. Andernfalls wird die schrittweise transparente fortgeführt.  
  
 Wenn der Debugger keinen Stepper verwendet, um eine Methode einzugeben, wird der nicht zugeordnete Code nicht notwendigerweise überschrit.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
