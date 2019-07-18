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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0a273c54559e8e297e09740ba9c770ce12d72d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760587"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask-Methode
Legt einen Wert, der den Typ von nicht zugeordnetem Code gibt an, in dem die Ausführung angehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mask`  
 [in] Der Wert der CorDebugUnmappedStop-Enumeration, die den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung angehalten wird.  
  
 Der Standardwert ist STOP_OTHER_UNMAPPED. Der Wert STOP_UNMANAGED ist nur gültig mit der interop-Debuggen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Debugger eine just-in-Time-Kompilierung (JIT), die keine entsprechende Zuordnung Microsoft intermediate Language (MSIL) aufweist findet, hält er Ausführung, wenn das Flag, das diesen Typ von nicht zugeordnetem Code angeben festgelegt wurde; Andernfalls wird die transparente schrittweise Ausführung fortgesetzt.  
  
 Wenn der Debugger eine zugeordnetem nicht verwendet, eine Methode einzugeben, wird nicht es unbedingt nicht zugeordnetem Code überspringen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
