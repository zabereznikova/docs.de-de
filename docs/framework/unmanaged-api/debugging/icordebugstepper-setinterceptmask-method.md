---
title: ICorDebugStepper::SetInterceptMask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ef03b63c4af79c01ba9962fcc6f106b3141b576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask-Methode
Legt einen Wert, der angibt, die Typen von Code, der durchlaufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mask`  
 [in] Eine Kombination von Werten CorDebugIntercept-Enumeration, die die Codetypen angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Bit für einen Interceptor festgelegt ist, wird der zugeordnetem vervollständigt, wenn es sich bei der jeweiligen Typ der abfangen Code aufgetreten ist. Wenn das Bit deaktiviert ist, wird die abgefangene Code übersprungen.  
  
 Die `SetInterceptMask` Methode möglicherweise unvorhergesehene Interaktionen mit [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (aus Sicht des Benutzers). Z. B. wenn nur sichtbar (d. h.-interner) Teil des Initialisierungscodes für die Klasse verfügt nicht über die Zuordnungsinformationen und STOP_NO_MAPPING_INFO nicht festgelegt ist (finden Sie unter der [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) Methode und die CorDebugUnmappedStop-Enumeration), wird die Initialisierung der Klasse die zugeordnetem überspringen. Standardmäßig wird nur der INTERCEPT_NONE-Wert, der die `CorDebugIntercept` Enumeration verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
