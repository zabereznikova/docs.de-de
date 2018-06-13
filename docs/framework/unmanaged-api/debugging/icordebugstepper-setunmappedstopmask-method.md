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
ms.openlocfilehash: dc4e51ec60c7526f36bbe4909bec91a527e0862c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419909"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask-Methode
Legt einen Wert, der den Typ des nicht zugeordneten Codes angibt, in dem die Ausführung angehalten wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mask`  
 [in] Der Wert der CorDebugUnmappedStop-Enumeration, die den Typ des nicht zugeordneten Codes angibt, in dem der Debugger die Ausführung angehalten wird.  
  
 Der Standardwert ist STOP_OTHER_UNMAPPED. Der Wert STOP_UNMANAGED ist nur gültig, wenn Interop-Debuggen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Debugger eine just-in-Time (JIT)-Kompilierung, die keine entsprechende Zuordnung in die Microsoft intermediate Language (MSIL) aufweist findet, hält der Ausführung an, wenn die Angabe dieses Typs von nicht zugeordnetem Code Flag festgelegt wurde; Andernfalls wird die transparente schrittweise Ausführung fortgesetzt.  
  
 Wenn der Debugger eine zugeordnetem eingeben eine Methode verwendet, wird nicht es unbedingt nicht zugeordnetem Code überspringen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
