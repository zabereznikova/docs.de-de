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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37b644227a6085352bed682f0ddd7c3455b54895
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760706"
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask-Methode
Legt einen Wert, der angibt, die Typen von Code, der durchlaufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mask`  
 [in] Eine Kombination von Werten CorDebugIntercept-Enumeration, die die Codetypen angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Bit für einen Interceptor festgelegt ist, wird die zugeordnetem abgeschlossen, wenn der angegebene Typ des Abfangen von Code erkannt wird. Wenn das Bit deaktiviert ist, wird die abgefangene Code übersprungen.  
  
 Die `SetInterceptMask` Methode möglicherweise unvorhergesehene Interaktionen mit [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (aus Sicht des Benutzers). Z. B. wenn nur sichtbare (d. h. nicht-interne) Teil des Initialisierungscodes für die Klasse verfügt nicht über die Zuordnungsinformationen und STOP_NO_MAPPING_INFO ist nicht festgelegt (finden Sie unter der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode und die CorDebugUnmappedStop-Enumeration), wird die klasseninitialisierung die zugeordnetem überspringen. Standardmäßig wird nur der INTERCEPT_NONE-Wert, der die `CorDebugIntercept` -Enumeration verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
