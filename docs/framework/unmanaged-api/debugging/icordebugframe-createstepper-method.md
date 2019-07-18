---
title: ICorDebugFrame::CreateStepper-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd105a5cbdb857aaa902e60968ff1d94473259b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754239"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper-Methode
Ruft ab eine zugeordnetem, die mit dem Debugger zum schrittweisen Operationen in Bezug auf diesem ICorDebugFrame ausführen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppStepper`  
 [out] Ein Zeiger auf die Adresse des ein ICorDebugStepper-Objekt, das mit dem Debugger zum schrittweisen Operationen in Bezug auf den aktuellen Frame ausführen kann.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Frame nicht aktiv ist, müssen das zugeordnetem-Objekt in der Regel auf den Frame zurück, bevor der Schritt abgeschlossen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
