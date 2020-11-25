---
title: ICorDebugStepper::SetInterceptMask-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
ms.openlocfilehash: 814bf87039ef57056f13994af1b873f8f57c7804
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718214"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask-Methode

Legt einen Wert fest, der die Typen von Code angibt, die in Einzelschritten werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mask`  
 in Eine Kombination von Werten der CorDebugIntercept-Enumeration, die die Codetypen angibt.  
  
## <a name="remarks"></a>Hinweise  

 Wenn das Bit für einen Interceptor festgelegt ist, wird der Stepper vervollständigt, wenn der angegebene Typ des Abfang Codes auftritt. Wenn das Bit deaktiviert ist, wird der abfängt Code übersprungen.  
  
 Die- `SetInterceptMask` Methode hat möglicherweise unvorhergesehene Interaktionen mit [ICorDebugStepper:: seetunmappedstopmask](icordebugstepper-setunmappedstopmask-method.md) (aus Sicht des Benutzers). Wenn z. b. der einzige sichtbare (d. h. nicht interne) Teil des Initialisierungs Codes der Klasse keine Mappinginformationen hat und STOP_NO_MAPPING_INFO nicht festgelegt ist (siehe die [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) -Methode und die CorDebugUnmappedStop-Enumeration), wird der Stepper die Initialisierung der Klasse überschreiten. Standardmäßig wird nur der INTERCEPT_NONE Wert der- `CorDebugIntercept` Enumeration verwendet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
